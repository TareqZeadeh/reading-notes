# Java Imports
## Packages and Import
#### Java classes can be grouped together in packages. A package name is the same as the directory (folder) name which contains the .java files.  
#### You declare packages when you define your Java program, and you name the packages you want to use from other libraries in an import statement.
#### Package declaration syntax: The statement order is as follows. Comments can go anywhere.
1. Package statment (optional).
2. Imports (optional).
3. Class or interface definitions.
#### Imports: three options: The JOptionPane class is in the swing package, which is located in the javax package. The wildcard character (*) is used to specify that all classes with that package are available to your program. 
##### -Classes can be specified explicitly on import instead of using the wildcard character.
##### -Alternately we can the fully qualified class name without an import.
#### Common imports: There are 166 packages containing 3279 classes and interfaces in Java 5. However, only a few packages are used in most programming. GUI programs typically use at least the first three imports.
1. import java.awt.*;	Common GUI elements.
2. import java.awt.event.*;	The most common GUI event listeners.
3. import javax.swing.*;	More common GUI elements. Note "javax".
4. import java.util.*;	Data structures (Collections), time, Scanner, etc classes.
5. import java.io.*;	Input-output classes.
6. import java.text.*;	Some formatting classes.
7. import java.util.regex.*;	Regular expression classes.
#### import FAQ 
1. Q: Does importing all classes in a package make my object file (.class or .jar) larger?
A: No, import only tells the compiler where to look for symbols.

2. Q: Is it less efficient to import all classes than only the classes I need?
A: No. The search for names is very efficient so there is no effective difference.

3. Q: Doesn't it provide better documentation to import each class explicitly?
A: This shows good intentions, but ...

*-It's hard to remember to remove classes when they are no longer used, so the import list is surprisingly often wrong. It can seriously slow down reading because unusual or unexpected class imports make me look for that class, only to discover that it must have been used in an earlier version.

*-Explicit class imports permit accidentally defining classes with names that conflict with the standard library names. This is very bad. Using "*" to import all classes prevents this dangerous naming accident.

*-It's annoying to always update this list, altho if you use NetBeans, fixing the list is only a click away (see below).
4. Q: I've imported java.awt.*, why do I also need java.awt.event.*?
A: The wildcard "*" only makes the classes in this package visible, not any of the subpackages.

5. Q: Why don't I need an import to use String, System, etc?
A: All classes in the java.lang package are visible without an import.

6. Q: Is the order of the imports important?
A: No. Group them for readability.
#### Static imports in Java 5: Java 5 added an import static option that allows static variables (typically constants) to be referenced without qualifying them with a class name.
##### Adding this "feature" wasn't the best idea because it leads to name pollution and confusion about which class constants come from.

------------------------------------------------------------------------------------------------------------
# Different types of loops in Java
#### looping is a feature which facilitates the execution of a set of instructions until the controlling Boolean-expression evaluates to false.

#### There is different types of loops to fit any programming need. Each loop has its own purpose and a suitable use case to serve.
#### Type of loops: 
1. Simple for loop.
2. Enhanced for-each loop.
3. While loop.
4. Do-While loop.
#### For Loop : A for loop is a control structure that allows us to repeat certain operations by incrementing and evaluating a loop counter.
#### While Loop : It repeats a statement or a block of statements while its controlling Boolean-expression is true.
#### Do-While Loop : The do-while loop works just like the while loop except for the fact that the first condition evaluation happens after the first iteration of the loop.
#### Conclusion: 