# Relationships in JPA 
#### One-to-One RelationShip
- To define this relationship in Jpa we use the @OneToOne annotation.
- We can optionally use @RestResources to customize our end point. 
- Different name for each resource is mandatory.
- To expose each entity in Jpa we use a repository interface which will be extending from CRUD Repository or any child of it.
- Sending get request to an endpoint would return an empty object if no post requests was sent.
- We use the PUT method to retrieve the JSON object or Delete to delete a record.


#### One-to-Many RelationShip
- One to many can be declared the same as one to one relationship in addition to many to one.
- It can also have optional @RestResources to customize endpoints.
- to Expose it we need the same repository interface that extends CRUDRepository.
- Use the PUT request to associate the repository with the association.

#### Many-to-Many Relationship
- Is the same as the previous realtionships.
- needs the same steps to initialize and access and edit.

#### Testing Endpoints 
- Define a class that injects a TestRestTemplate.
- Define the endpoints as strings.
- Declare @Test method to start testing.
- Make an object for each class you want to test the relation on.
- Use postEntity to the specific objects.
- use the HttpHeaders to add the headers of the request.
- assertEquals the response for each.

# Integration Testing in Spring
- We use the following dependencies for testing in spring :
    - Spring Test.
    - Junit Jupiter.

- We use the Web application context annotation to wire the object of it which will add all the beans, controllers and classes.

- MockMVC class encapsulates beans of web application and makes them ready for testing.

- to Verify testing configuration we should verify that : 
    - Check if web application context is loaded.
    - check the right servlet context is instance of the web application context.

- We use perform method which will make a get request.
- followed by andDo(Print()) will print the request and response.
- andExpect(view().name("test.html")) will expect a specific view to be returned.
- We can also sending requests with perform method including path variables with this syntax perform("request/{id}" , "123")
- Also sending post requests can be achieved using mockMvc Library the same mechanism for get requests.