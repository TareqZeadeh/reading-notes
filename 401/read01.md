# Java Basics
## Variables : 
### kinds of variables
1. Instance Variables (Non-Static Fields): objects store their individual states in "non-static fields", that is, fields declared without the (static) keyword, Non-static fields are also known as instance variables.
2. Class Variables (Static Fields): A class variable is any field declared with the static modifier, this tells the compiler that there is exactly one copy of this variable in existence, regardless of how many times the class has been instantiated.
3. Local Variables : Similar to how an object stores its state in fields, a method will often store its temporary state in local variables.
4. Parameters : parameters are always classified as "variables" not "fields". 
### Naming : The rules and conventions for naming your variables can be summarized as follows:
1. Variable names are case-sensitive. A variable's name can be any legal identifier ,The convention, is to always begin your variable names with a letter, not "$" or "_" and White space is not permitted.
2. Subsequent characters may be letters, digits, dollar signs, or underscore characters, Conventions (and common sense) apply to this rule as well. When choosing a name for your variables, use full words instead of cryptic abbreviations and also keep in mind that the name you choose must not be a keyword or reserved word.
3. If the name you choose consists of only one word, spell that word in all lowercase letters, If your variable stores a constant value, such as static final int NUM_GEARS = 6, the convention changes slightly, capitalizing every letter and separating subsequent words with the underscore character. By convention, the underscore character is never used elsewhere.
### Primitive Data Types:
1. byte
2. short
3. int
4. long
5. float
6. double
7. boolean
8. char
### Arrays : An array is a container object that holds a fixed number of values of a single type. The length of an array is established when the array is created. After creation, its length is fixed.

## Operators : Operators are special symbols that perform specific operations on one, two, or three operands, and then return a result.

### The operators are listed according to precedence order. The closer to the top, the higher its precedence.
 Operators           	        Precedence

1. postfix	                    expr++ expr--
2. unary	                    ++expr --expr +expr -expr ~ !
3. multiplicative   	        * / %
4. additive	                    + -
5. shift	                    << >> >>>
6. relational      	            < > <= >= instanceof
7. equality	                    == !=
8. bitwise AND	                &
9. bitwise exclusive OR     	^
10. bitwise inclusive OR    	|
11. logical AND	                &&
12. logical OR	                ||
13. ternary             	    ? :
14. assignment          	    = += -= *= /= %= &= ^= |= <<= >>= >>>=

## Expressions, Statements, and Blocks
### Expressions : An expression is a construct made up of variables, operators, and method invocations, which are constructed according to the syntax of the language, that evaluates to a single value. 
### Statements : A statement forms a complete unit of execution.
### Blocks : A block is a group of zero or more statements between balanced braces and can be used anywhere a single statement is allowed.

## Control Flow Statements 
### Control flow statements, however, break up the flow of execution by employing decision making, looping, and branching, enabling your program to conditionally execute particular blocks of code.
#### The if-then and if-then-else Statements
1. if-then Statement: It tells your program to execute a certain section of code only if a particular test evaluates to true.
2. if-then-else Statement: The if-then-else statement provides a secondary path of execution when an "if" clause evaluates to false.
#### The switch Statement: The switch statement can have a number of possible execution paths.

#### The while and do-while Statements :
1. The while statement continually executes a block of statements while a particular condition is true.
2. The difference between do-while and while is that do-while evaluates its expression at the bottom of the loop instead of the top. Therefore, the statements within the do block are always executed at least once.
#### The for Statement: The for statement provides a compact way to iterate over a range of values. 
#### Branching Statements: 
1. The break Statement : The break statement has two forms: labeled and unlabeled. You can use an unlabeled break to terminate a for, while, switch or do-while loop, The labeled break terminates an outer statement.
2. The continue Statement : The continue statement skips the current iteration of a for, while , or do-while loop. The unlabeled form skips to the end of the innermost loop's body and evaluates the boolean expression that controls the loop. The labeled continue statement skips the current iteration of an outer loop marked with the given label.
3. The return Statement : The return statement exits from the current method, and control flow returns to where the method was invoked. The return statement has two forms: one that returns a value, and one that doesn't. To return a value, simply put the value (or an expression that calculates the value) after the return keyword.

# The first response in this Reddit thread on compiling 
### When we want to write our programs, putting everything in 1's and 0's (whish is the  machine language) would be very difficult. So we made higher level languages like Java to write code in.
### When we compile code, the compilor takes the program that we wrote, and converts it into the program the computer can understand (converts from Java to machine language).
### Sometimes our code does or does not compile. This means the compilor is checking to make sure our program is written correctly according to the rules of the programming language.