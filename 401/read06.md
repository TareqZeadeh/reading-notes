# Inheritance and Interfaces :

## Inheritance : A lot of object kinds have some properties that is in common with another object , In java A class can have only one super class and as much sub-classes as it needs .
- Each class extends the object class as a super class .

- Sub classes can use it's parent properties and methods which are public or protectd , however it cant access private members of it's parent class . 
- Casting objects : We can cast object to expose more features of the sub class to the super class and some more properties to know that a sub class is actually a super class instance .
- Over riding a method is editing a method that have the same signature in a sub class to consume as needed .
- Default and static methods are inherited like instance methods .
- Polymorphism : is the ability of a super class to refer to a child of it to get appropriate and more extensible use of the object .
- If a sub class hav a field with the same name in the super class will hide the one in the super class and can only be called using super keyword .
- Super keyword can be used to invoke an overriden method or calling the super class constructor which is required to declare the sub class .
- clone method can be used by implementing Clonable interface .
- equals method is used to determine if two objects are equal .
- get class method will return the runtime class of the instance .
- hash code returns the hash code of the object .
- to string returns a string version of the object .
- final methods can't be overriden after declared , also classes can be final and can't be subclassed .
- Abstract classes are : classes that may or may not have abstract methods , it can contain fields , static methods , instance variables .
- abstract classes may be used when classes are closely related to each other in fields and methods .


## Interface : Is a group of empty body methods that will be exposed to specific classes to make the class functionality more formal to handle , When an interface is implemented all the methods must be exposed in the class .
- Defining an interface : Definition contains access modifier , interface keyword , name of interface followed by : 
parent interfaces if exists .

- Body of interface : Body contains abstract , default and static methods all of the methods are public by default , also an interface can contain constants which are public , final , static by default .
- Implementing interface : We use the word implements , class can implement more than one interface if required , 
When implementing an interface all of the methods must be declared in the class 
- Interface as a type : Interfaces can be used as a reference data type but with a class that implements that interface .
- To extend the interface : You can either declare a new interface that extends the old one , add methods as default methods with their declaration .
- Default methods : are methods defined with the default keyword that have it's implementation on the interface , and must'nt be redeclared in the class that implements the interface .
- Extending class with default methods : you can don't mention it which will inherit it , declare it which makes it abstract , define it to override it .
- In addition to default methods we use static methods which is shared by instances that contains it also they are defined in the interface itself and should include the static keyword .

## Package : Packages are directories that organizes java's related classes and interfaces , since java programs consists of thousands of classes it will be better to organize the classes in packages , Java platform API have alot of classes which are organized in specific packages .