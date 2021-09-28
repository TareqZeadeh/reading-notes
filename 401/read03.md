# Primitives vs. Objects
### Java has a two-fold type system consisting of primitives such as int, boolean and reference types such as Integer, Boolean. Every primitive type corresponds to a reference type.
### Every object contains a single value of the corresponding primitive type. The wrapper classes are immutable  and are final.
### Under the hood, Java performs a conversion between the primitive and reference types if an actual type is different from the declared one:
1. Integer j = 1;          // autoboxing
2. int i = new Integer(1); // unboxing
### The process of converting a primitive type to a reference one is called autoboxing, the opposite process is called unboxing.
### The primitive type variables have the following impact on the memory:
1. boolean – 1 bit
2. byte – 8 bits
3. short, char – 16 bits
4. int, float – 32 bits
5. long, double – 64 bits
### A single instance of a reference occupies 128 bits except for Long and Double which occupy 192 bits:
1. Boolean – 128 bits
2. Byte – 128 bits
3. Short, Character – 128 bits
4. Integer, Float – 128 bits
5. Long, Double – 192 bits
### single-element arrays of primitive types are almost always more expensive (except for long and double) than the corresponding reference type.
### The performance of a Java code is quite a subtle issue, it depends very much on the hardware on which the code runs, on the compiler that might perform certain optimizations, on the state of the virtual machine, on the activity of other processes in the operating system.

### As we have already mentioned, the primitive types live in the stack while the reference types live in the heap. This is a dominant factor that determines how fast the objects get be accessed.
### The primitive types may acquire values only from their domains, while the reference types might acquire a value (null) that in some sense doesn't belong to their domains.
### when a primitive type variable has a value that is equal to its type default one, we should find out whether the variable has been really initialized.

### There's no such a problem with a wrapper class variables since the null value is quite an evident indication that the variable hasn't been initialized.
### the primitive types are much faster and require much less memory. Therefore, we might want to prefer using them. On the other hand, current Java language specification doesn't allow usage of primitive types in the parametrized types (generics),  in the Java collections or the Reflection API. When our application needs collections with a big number of elements, we should consider using arrays with as more “economical” type as possible, as it's illustrated on the plot above.
---------------------------------------------------------------
# Exceptions in Java
### An exception is an event, which occurs during the execution of a program, that disrupts the normal flow of the program's instructions.
### When an error occurs within a method, the method creates an object and hands it off to the runtime system. The object, called an exception object, contains information about the error, including its type and the state of the program when the error occurred. Creating an exception object and handing it to the runtime system is called throwing an exception.
### After a method throws an exception, the runtime system attempts to find something to handle it. The set of possible "somethings" to handle the exception is the ordered list of methods that had been called to get to the method where the error occurred. The list of methods is known as the call stack .
### The runtime system searches the call stack for a method that contains a block of code that can handle the exception. This block of code is called an exception handler.
### Valid Java programming language code must honor the Catch or Specify Requirement. This means that code that might throw certain exceptions must be enclosed by either of the following:

1. A try statement that catches the exception. The try must provide a handler for the exception, as described in Catching and Handling Exceptions.
2. A method that specifies that it can throw the exception. The method must provide a throws clause that lists the exception, as described in Specifying the Exceptions Thrown by a Method.
### Code that fails to honor the Catch or Specify Requirement will not compile.
## The Three Kinds of Exceptions
### The first kind of exception is the checked exception. These are exceptional conditions that a well-written application should anticipate and recover from. 
### Checked exceptions are subject to the Catch or Specify Requirement. All exceptions are checked exceptions, except for those indicated by Error, RuntimeException, and their subclasses.
### The second kind of exception is the error. These are exceptional conditions that are external to the application, and that the application usually cannot anticipate or recover from.
### Errors are not subject to the Catch or Specify Requirement. Errors are those exceptions indicated by Error and its subclasses.
### The third kind of exception is the runtime exception. These are exceptional conditions that are internal to the application, and that the application usually cannot anticipate or recover from. These usually indicate programming bugs, such as logic errors or improper use of an API.
### Runtime exceptions are not subject to the Catch or Specify Requirement. Runtime exceptions are those indicated by RuntimeException and its subclasses.
### Errors and runtime exceptions are collectively known as unchecked exceptions.
---------------------------------------------
# Using Scanner to read in a file in Java
### Objects of type Scanner are useful for breaking down formatted input into tokens and translating individual tokens according to their data type.
### By default, a scanner uses white space to separate tokens. (White space characters include blanks, tabs, and line terminators. For the full list, refer to the documentation for Character.isWhitespace.) 
### 