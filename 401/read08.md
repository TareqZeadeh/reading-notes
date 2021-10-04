# SOLID 
## SOLID : stands for the five principles in OOD that considers maintaining , refactoring , debugging , avoid code smells principles .
## S - Single-responsiblity Principle :
- A class should have one reason to change (one functionalitiy) .
- Each class should be concerened about it's own funcionality only .
- In real life imagine important tasks that depends on unrelated tasks .
## O - Open-closed Principle : Objects or instances should be open for extension and closed for modification .
- That means we should be able to extend the class without modifiying it .
- To come across Open closed principle Interfaces should be implemented .
- When using interfaces functionality can be extended without modifiying the class itself .
- extending the bilities in phone without having the access to modify it .
## L - Liskov Substitution Principle : Every derived class can be substituted from it's parent class .
- The child class should be combatible with it's parent functionality and that what is liskov principle is about .
- Ensures that each child class is able to implement the parents attitude and behavior .
## I - Interface Segregation Principle :You shouldn't force a user to implement useless methods which he wouldn't use .
- Making interfaces can divide the task into the classes that needs it .
- Making interfaces serves a specific group or classes .
- Managing the attitude of classes by interfaces .
- It's about depending on smaller useful interface other than one big interface and implementing each method when using it or not .
## D - Dependency Inversion Principle : Entities should be abstracted and decoupled .
- both high level and low level modules depends on abstraction .
- This principle is concerned with abstraction and not counting on another class or (sub classes ) .