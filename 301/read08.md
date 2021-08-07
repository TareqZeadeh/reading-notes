# RESTful web API design.
## 1.What does REST stand for?
#### REST is an architectural style for building distributed systems based on hypermedia. REST is independent of any underlying protocol and is not necessarily tied to HTTP.
## 2.REST APIs are designed around a __resources__.
#### REST APIs are designed around resources, which are any kind of object, data, or service that can be accessed by the client.
## 3.What is an identifer of a resource? Give an example.
#### A resource has an identifier, which is a URI that uniquely identifies that resource. For example, the URI for a particular customer order might be:``` https://adventure-works.com/orders/1```
## 4.What are the most common HTTP verbs?
#### The most common operations are GET, POST, PUT, PATCH, and DELETE.
## 5.What should the URIs be based on?
#### URIs should be based on nouns (the resource) and not verbs (the operations on the resource).
## 6.Give an example of a good URI.
#### ```https://tareqzeadeh.github.io/reading-notes/```
## 7.What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?
#### **Chatty** web APIs expose a large number of small resources. Such an API may require a client application to send multiple requests to find all of the data that it requires , **which is a Bad thing.**
## 8.What status code does a successful **GET** request return?
#### A successful GET method typically returns HTTP status code 200 (OK).
## 9.What status code does an unsuccessful **GET** request return?
#### An unsuccessful GET method return 404 (Not Found).
## 10.What status code does a successful POST request return?
#### If a POST method creates a new resource, it returns HTTP status code 201 (Created).
## 11.What status code does a successful DELETE request return?
#### If the delete operation is successful, the web server should respond with HTTP status code 204 (No Content).
