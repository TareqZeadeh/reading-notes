# Read: Class 33 Read: 33 - GraphQL @connection

## [GraphQL @connection section](https://docs.amplify.aws/cli/graphql-transformer/connection)

### @connection

1. The @connection directive enables you to specify relationships between @model types.
1. Definition
   - `directive @connection(keyName: String, fields: [String!]) on FIELD_DEFINITION`
1. The fields argument can be provided and indicates which fields can be queried by to get connected objects.
1. The keyName argument can optionally be used to specify the name of secondary index (an index that was set up using @key) that should be queried from the other type in the relationship.

### Has One

one-to-one connection where a project has one team:

```graphql
type Project @model {
  id: ID!
  name: String
  team: Team @connection
}
type Team @model {
  id: ID!
  name: String!
}
```

1. A Has One @connection can only reference the primary index of a model (ie. it cannot specify a “keyName”).

### Has many

```graphql
type Post @model {
  id: ID!
  title: String!
  comments: [Comment] @connection(keyName: "byPost", fields: ["id"])
}
type Comment @model @key(name: "byPost", fields: ["postID", "content"]) {
  id: ID!
  postID: ID!
  content: String!
}
```

1. one-to-many connection needs an @key that allows comments to be queried by the postID and the connection uses this key to get all comments whose postID is the id of the post was called on.

### Belongs to

You can make a connection bi-directional by adding a many-to-one connection to types that already have a one-to-many connection.

```graphql
type Post @model {
  id: ID!
  title: String!
  comments: [Comment] @connection(keyName: "byPost", fields: ["id"])
}
type Comment @model @key(name: "byPost", fields: ["postID", "content"]) {
  id: ID!
  postID: ID!
  content: String!
  post: Post @connection(fields: ["postID"])
}
```

### Many-to-many connections

You can implement many to many using two 1-M @connections, an @key, and a joining @model.

```graphql
type Post @model {
  id: ID!
  title: String!
  editors: [PostEditor] @connection(keyName: "byPost", fields: ["id"])
}
# Create a join model and disable queries as you don't need them
# and can query through Post.editors and User.posts
type PostEditor
  @model(queries: null)
  @key(name: "byPost", fields: ["postID", "editorID"])
  @key(name: "byEditor", fields: ["editorID", "postID"]) {
  id: ID!
  postID: ID!
  editorID: ID!
  post: Post! @connection(fields: ["postID"])
  editor: User! @connection(fields: ["editorID"])
}
type User @model {
  id: ID!
  username: String!
  posts: [PostEditor] @connection(keyName: "byEditor", fields: ["id"])
}
```

### Limit

The default number of nested objects is 100. You can override this behavior by setting the limit argument.

### Generates

In order to keep connection queries fast and efficient, the GraphQL transform manages global secondary indexes (GSIs) on the generated tables on your behalf when using @connection