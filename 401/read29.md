# Room

## [Overview: Saving data with Room](https://developer.android.com/training/data-storage/room)

1. The Room persistence library provides an abstraction layer over SQLite to allow fluent database access while harnessing the full power of SQLite.
   - Compile-time verification of SQL queries.
   - Convenience annotations that minimize repetitive and error-prone boilerplate code.
   - Streamlined database migration paths.

### Primary components

1. There are three major components in Room:

   - The database class that holds the database and serves as the main access point for the underlying connection to your app's persisted data.
   - Data entities that represent tables in your app's database.
   - Data access objects (DAOs) that provide methods that your app can use to query, update, insert, and delete data in the database.

![Diagram of Room library architecture.](https://developer.android.com/images/training/data-storage/room_architecture.png)

1. The database class must satisfy the following conditions:

   - The class must be annotated with a @Database annotation that includes an entities array that lists all of the data entities associated with the database.
   - The class must be an abstract class that extends RoomDatabase.
   - For each DAO class that is associated with the database, the database class must define an abstract method that has zero arguments and returns an instance of the DAO class.

## [Defining entities in Room](https://developer.android.com/training/data-storage/room/defining-data)

1. Each entity corresponds to a table in the associated Room database, and each instance of an entity represents a row of data in the corresponding table.
1. By default, Room uses the class name as the database table name. If you want the table to have a different name, set the tableName property of the @Entity annotation.

### Define a primary key

1. Each Room entity must define a primary key that uniquely identifies each row in the corresponding database table.
1. If you need instances of an entity to be uniquely identified by a combination of multiple columns, you can define a composite primary key by listing those columns in the primaryKeys property of @Entity

### Ignore fields

1. By default, Room creates a column for each field that's defined in the entity. If an entity has fields that you don't want to persist, you can annotate them using @Ignore

### Provide table search support

1. Room supports several types of annotations that make it easier for you to search for details in your database's tables.
1. If your app requires very quick access to database information through full-text search (FTS), have your entities backed by a virtual table that uses either the FTS3 or FTS4 SQLite extension module To use this capability,add the @Fts3 or @Fts4 annotation to a given entity,

### Index specific columns

1. To add indices to an entity, include the indices property within the @Entity annotation, listing the names of the columns that you want to include in the index or composite index.

### Include AutoValue-based objects

1. When using classes annotated with @AutoValue as entities, you can annotate the class's abstract methods using @PrimaryKey, @ColumnInfo, @Embedded, and @Relation. When using these annotations, however, you must include the @CopyAnnotations annotation each time so that Room can interpret the methods' auto-generated implementations properly.

## [Related entities in Room](https://developer.android.com/training/data-storage/room/relationships)

### Create embedded objects

1. if the object contains several fields. In these situations, you can use the @Embedded annotation to represent an object that you'd like to decompose into its subfields within a table.

### Define one-to-one relationships

1. create a new data class where each instance holds an instance of the parent entity and the corresponding instance of the child entity. Add the @Relation annotation to the instance of the child entity, with parentColumn set to the name of the primary key column of the parent entity and entityColumn set to the name of the column of the child entity that references the parent entity's primary key.
1. add a method to the DAO class that returns all instances of the data class that pairs the parent entity and the child entity.

### Define one-to-many relationships

```java
public class UserWithPlaylists {
    @Embedded public User user;
    @Relation(
         parentColumn = "userId",
         entityColumn = "userCreatorId"
    )
    public List<Playlist> playlists;
}
@Transaction
@Query("SELECT * FROM User")
public List<UserWithPlaylists> getUsersWithPlaylists();
```

### Define many-to-many relationships

```java
@Entity
public class Playlist {
    @PrimaryKey public long playlistId;
    public String playlistName;
}
@Entity
public class Song {
    @PrimaryKey public long songId;
    public String songName;
    public String artist;
}
@Entity(primaryKeys = {"playlistId", "songId"})
public class PlaylistSongCrossRef {
    public long playlistId;
    public long songId;
}
public class PlaylistWithSongs {
    @Embedded public Playlist playlist;
    @Relation(
         parentColumn = "playlistId",
         entityColumn = "songId",
         associateBy = @Junction(PlaylistSongCrossref.class)
    )
    public List<Song> songs;
}
public class SongWithPlaylists {
    @Embedded public Song song;
    @Relation(
         parentColumn = "songId",
         entityColumn = "playlistId",
         associateBy = @Junction(PlaylistSongCrossref.class)
    )
    public List<Playlist> playlists;
}
```

### Define nested relationships

```java
@Entity
public class User {
    @PrimaryKey public long userId;
    public String name;
    public int age;
}
@Entity
public class Playlist {
    @PrimaryKey public long playlistId;
    public long userCreatorId;
    public String playlistName;
}
@Entity
public class Song {
    @PrimaryKey public long songId;
    public String songName;
    public String artist;
}
@Entity(primaryKeys = {"playlistId", "songId"})
public class PlaylistSongCrossRef {
    public long playlistId;
    public long songId;
}
```

```java
public class PlaylistWithSongs {
    @Embedded public Playlist playlist;
    @Relation(
         parentColumn = "playlistId",
         entityColumn = "songId",
         associateBy = Junction(PlaylistSongCrossRef.class)
    )
    public List<Song> songs;
}
```

```java
public class UserWithPlaylistsAndSongs {
    @Embedded public User user;
    @Relation(
        entity = Playlist.class,
        parentColumn = "userId",
        entityColumn = "userCreatorId"
    )
    public List<PlaylistWithSongs> playlists;
}
```

```java
@Transaction
@Query("SELECT * FROM User")
public List<UserWithPlaylistsAndSongs> getUsersWithPlaylistsAndSongs();
```

![Diagram of relationship classes in the music streaming app example.](https://developer.android.com/images/training/data-storage/room_nested_relationships.png)

## [Accessing data with Room](https://developer.android.com/training/data-storage/room/accessing-data#java)

1. You can define each DAO as either an interface or an abstract class. For basic use cases, you should usually use an interface. In either case, you must always annotate your DAOs with @Dao
1. There are two types of DAO methods that define database interactions:

   - Convenience methods that let you insert, update, and delete rows in your database without writing any SQL code.
   - Query methods that let you write your own SQL query to interact with the database.

### Insert

1. The @Insert annotation allows you to define methods that insert their parameters into the appropriate table in the database.
1. @Insert method must be either an instance of a Room data entity class annotated with @Entity or a collection of data entity class instances.

### Update

1. The @Update annotation allows you to define methods that update specific rows in a database table. Similarly to @Insert methods, @Update methods accept data entity instances as parameters.

### Delete

1. The @Delete annotation allows you to define methods that delete specific rows from a database table. Similarly to @Insert methods, @Delete methods accept data entity instances as parameters.

### Query methods

1. The @Query annotation allows you to write SQL statements and expose them as DAO methods.

### Return a subset of a table's columns

```java
public class NameTuple {
    @ColumnInfo(name = "first_name")
    public String firstName;
    @ColumnInfo(name = "last_name")
    @NonNull
    public String lastName;
}
@Query("SELECT first_name, last_name FROM user")
public List<NameTuple> loadFullName();
```

### Pass simple parameters to a query

```java
@Query("SELECT * FROM user WHERE age > :minAge")
public User[] loadAllUsersOlderThan(int minAge);
@Query("SELECT * FROM user WHERE age BETWEEN :minAge AND :maxAge")
public User[] loadAllUsersBetweenAges(int minAge, int maxAge);
@Query("SELECT * FROM user WHERE first_name LIKE :search " + "OR last_name LIKE :search")
public List<User> findUserWithName(String search);
```

### Pass a collection of parameters to a query

```java
@Query("SELECT * FROM user WHERE region IN (:regions)")
public List<User> loadUsersFromRegions(List<String> regions);
```

### Query multiple tables

```java
@Query("SELECT * FROM book " +
       "INNER JOIN loan ON loan.book_id = book.id " +
       "INNER JOIN user ON user.id = loan.user_id " +
       "WHERE user.name LIKE :userName")
public List<Book> findBooksBorrowedByNameSync(String userName);
```

### Paginated queries with the Paging library

```java
@Dao
interface UserDao {
  @Query("SELECT * FROM users WHERE label LIKE :query")
  PagingSource<Integer, User> pagingSource(String query);
}
```

### Direct cursor access

```java
@Dao
public interface UserDao {
    @Query("SELECT * FROM user WHERE age > :minAge LIMIT 5")
    public Cursor loadRawUsersOlderThan(int minAge);
}
```