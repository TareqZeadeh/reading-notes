# Read: Class 32 Read: 32 - Serverless and Amplify

## [Intro to Serverless](https://hackernoon.com/what-is-serverless-architecture-what-are-its-pros-and-cons-cc4b804022e9)

1. “Focus on your application, not the infrastructure”
1. Serverless applications are event-driven cloud-based systems where application development rely solely on a combination of third-party services, client-side logic and cloud-hosted remote procedure calls (Functions as a Service).
1. Traditional vs. Serverless Architecture
   ![Traditional vs. Serverless Architecture](https://hackernoon.com/hn-images/1*x_v5NRC3TTMt1MaYl1gMUg.jpeg)

### Pricing

1. The cost model of Serverless is execution-based: you’re charged for the number of executions.

### Networking

1. The downside is that Serverless functions are accessed only as private APIs. To access these you must set up an API Gateway. This doesn’t have an impact on your pricing or process, but it means you cannot directly access them through the usual IP.

### 3rd Party Dependencies

1. The winner here is based on the context. For simple applications with few dependencies, Serverless is the winner; for anything more complex, Traditional Architecture is the winner.

### Environments

Setting up different environments for Serverless is as easy as setting up a single environment.

### Timeout

With Serverless computing, there’s a hard 300-second timeout limit. Too complex or long-running functions aren’t good for Serverless

### Scale

It’s a tie between Serverless and Traditional Architecture.

### Functions as a Service (FaaS)

FaaS is an implementation of Serverless architectures where engineers can deploy an individual function or a piece of business logic.

### Stateless

With Serverless, everything is stateless, you can’t save a file to disk on one execution of your function and expect it to be there at the next.

### Ephemeral

FaaS are designed to spin up quickly, do their work and then shut down again.

### Event-triggered

Although functions can be invoked directly, yet they are usually triggered by events from other cloud services such as HTTP requests, new database entries or inbound message notifications.

### Scalable by default

### Fully managed by a Cloud vendor

### The Serverless App

1. Client Application
1. Web Server
1. Lambda functions (FaaS)
1. Security Token Service (STS)
1. User Authentication
1. Database

### Benefits of Serverless Architecture

1. cost
   - Cost of hiring backend
   - Reduced operational costs
1. Process agility
1. Reduced liability, no backend infrastructure to be responsible for.
1. Zero system administration.
1. Easier operational management.
1. Fosters adoption of Nanoservices, Microservices, SOA Principles.
1. Faster set up.
1. Scalable, no need to worry about the number of concurrent requests.
1. Monitoring out of the box.
1. Fosters innovation.

### Drawbacks of Serverless Architecture

1. Reduced overall control.
1. Vendor lock-in requires more trust for a third-party provider.
1. Additional exposure to risk requires more trust for a third party provider.
1. Security risk.
1. Disaster recovery risk
1. Cost is unpredictable because the number of executions is not predefined
1. All of these drawbacks can be mitigated with open-source alternatives but at the expense of cost benefits mentioned previously

#### From developer perspective

1. Immature technology results in component fragmentation, unclear best-practices.
1. Architectural complexity.
1. The discipline required against function sprawl.
1. Multi-tenancy means it’s technically possible that neighbor functions could hog the system resources behind the scenes.
1. Testing locally becomes tricky.
1. Significant restrictions on the local state.
1. Execution duration is capped.
1. Lack of operational tools

#### From user perspective

1. Unless architected correctly, an app could provide a poor user experience as a result of increased request latency.

## [AWS Amplify Kool-Aid](https://aws.amazon.com/amplify/)

1. With Amplify, you can configure app backends and connect your app in minutes, deploy static web apps in a few clicks, and easily manage app content outside the AWS console.
1. Benefits
   - Configure backends fast
   - Seamlessly connect frontends
   - Deploy in a few clicks
   - Easily manage content
1. Features & Tools
   - Authentication
   - API (GraphQL, REST)
   - Storage
   - Interactions
   - PubSub
   - DataStore
   - Functions
   - Analytics
   - AI/ML Predictions
   - Push Notifications
1. Deliver
1. Manage

## [GraphQL Intro ](https://docs.amplify.aws/cli/graphql-transformer/overview)

1. The GraphQL Transform provides a simple to use abstraction that helps you quickly create backends for your web and mobile applications on AWS.
1. The GraphQL Transform simplifies the process of developing, deploying, and maintaining GraphQL APIs.

### Create a GraphQL API

1. run: `amplify init`
1. After finishing the wizard run: `amplify add api`
1. Select the following options:

   - Select GraphQL
   - When asked if you have a schema, say No
   - Select one of the default samples; you can change this later
   - Choose to edit the schema and it will open the new schema.graphql in your editor

1. deploy your new API: `amplify push`

### Test the API

### Update schema

1. If you want to update your API, open your project’s `backend/api/~apiname~/schema.graphql` file (NOT the one in the `backend/api/~apiname~/build` folder) and edit it in your favorite code editor. You can compile the `backend/api/~apiname~/schema.graphql` by running:
   - `amplify api gql-compile`

### @model

1. Object types that are annotated with @model are top-level entities in the generated API.
1. Objects annotated with @model are stored in Amazon DynamoDB and are capable of being protected via @auth, related to other objects via @connection, and streamed into Amazon OpenSearch via @searchable

1. Usage
   - Define a GraphQL object type and annotate it with the @model directive to store objects of that type in DynamoDB and automatically configure CRUDL queries and mutations.
   - You may also override the names of any generated queries, mutations and subscriptions, or remove operations entirely.

### Generates

1. A single @model directive configures the following AWS resources:
   - An Amazon DynamoDB table with PAY_PER_REQUEST billing mode enabled by default.
   - An AWS AppSync DataSource configured to access the table above.
   - An AWS IAM role attached to the DataSource that allows AWS AppSync to call the above table on your behalf.
   - Up to 8 resolvers (create, update, delete, get, list, onCreate, onUpdate, onDelete) but this is configurable via the queries, mutations, and subscriptions arguments on the @model directive.
   - Input objects for create, update, and delete mutations.
   - Filter input objects that allow you to filter objects in list queries and connection fields.
   - For list queries the default number of objects returned is 100.