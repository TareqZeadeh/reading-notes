## Spring Request mapping 

- @RequestMapping annotation is one of the main annotation to map web requests to spring controller .
- Request mapping takes value which holds the path of the request and the HTTPrequest.get to determine the type of request we will use .
- HTTPrequest doesn't have a default value and should be determined .
- You can also specify a head sent with the request mapping pararmeter list as key value pair .
- Request can have multiple header by wrapping them in curly braces .
- Request mapping can accept types of data using accept header .
- The produce header can be sent to the mapping annotation with one or multiple values like json or xml .
- @PathVariable can be used in the request mapping and if it matches the same variable name it can be sent without value .
- More than one path variable can be used in the request mapping annotation .
- It can be sent as regex to ensure some specific data to be there .
- Request mapping can be used to easily map request parameters specified with @Requestparam annotation .
- Also we can determine our parameters in the body of the request mapping .
- When sending multiple values to the value attribute the request is mapped to the same method .
- Also multiple request methods can be mapped to the same controller . 
- To implement a fallback request for all methods we use the star sign as a place holder in the value attribute .
- Spring will throw if two request mappings have the same value header , method and return type .
- New Annotation introduced by spring based on request mapping : 
    - @GetMaping
    - @PostMaping
    - @PutMaping
    - @DeleteMaping
    - @PatchMaping


## Accessing Data with JPA

- First Steps to do is what I introduced previously is using the spring initializer : 

- Launch start.spring.io to Land on the home page .
- Specify Project ,team ,package names .
- Specify the language and version .
- Inject dependencies .
- Click on generate .
- Download the zip file which will contain your initialized project .


#### Defining a simple entity

- Starts by defining a class with it's members and constructor including getters and setters if wanted .
- Then You have to annotate the class with @Entity annotation .
- After that start by adding an id as a data member annotated with @Id and @GeneratedValue with (strategy = GenerationType.Auto) 
This means that the id value will be generated automatically .
- In entity the default constructor must be declared .
- The arg-Constructor is used to create objects and save in the database .


#### Create Simple Queries

- In order to make queries and operation to the entity we should make a new repository interface .
- That interface should extend JpaRepository to take all the operations on the database from Jpa .
- In that interface you are allowed to define methods by adding their signature to the interface .
- You can add data to the database by making an object of the entity class .
- Then use the save method to save the object in the database .


## Spring Data Repository 

- Every repository in spring data extends repository interface . 

#### CrudRepository

- Provide CRUD functions .
- If we don't the full functionality we can simply implement this repository .
- Provides all query abstractions needed in application .
- Example methods : count , find , findall .


#### PagingAndSortingRepository

- Provide pagination and sorting functions .

#### JpaRepository

- Extends  PagingAndSortingRepository and CrudRepository .
- Provides Jpa related methods like flushing deleting records .
- Easily implementing it and providing the method signature will implement the method for us .


##### Down Sides of Repositories : 
    - Couple the code to the library . 
    - By extending the CrudRpository we expose a whole set of methods which we want to gain more control on .