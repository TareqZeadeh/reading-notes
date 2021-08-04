# The JavaScript Call Stack - What It Is and Why It's Necessary
## 1.What is a ‘call’?
#### A call stack is a data structure that uses the Last In, First Out (LIFO) principle to temporarily store and manage function invocation **(call)**.
## 2.How many ‘calls’ can happen at once?
#### Since the call stack is single, function(s) execution, is done one at a time, from top to bottom. It means the call stack is synchronous.
## 3.What does LIFO mean?
#### It means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.
## 4.Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.
#### **Temporarily store**: When a function is invoked (called), the function, its parameters, and variables are pushed into the call stack to form a stack frame. This stack frame is a memory location in the stack. The memory is cleared when the function returns as it is pop out of the stack.
 ![](https://cdn-media-1.freecodecamp.org/images/QgR2uIk7tW0YNz0Xm8g0jAPeRFI0e4sCejsv)
 ## 5.What causes a Stack Overflow?
 #### A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.

 ### ================================================================================================================================================================================================================
# JavaScript error messages && debugging
## 1.What is a ‘refrence error’?
#### IT is an error occurs when you try to use a variable that is not declared yet.
## 2.What is a ‘syntax error’?
#### This occurs when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse.
## 3.What is a ‘range error’?
#### This type of error occurs when trying to tamper with the length of a certain object by making its length smaller than the original length, such as trying to change the length of an array in order to make it empty.
## 4. What is a ‘tyep error’?
#### This types of errors show up when the types (number, string and so on) you are trying to use or access are incompatible, like accessing a property in an undefined type of variable.
## 5.What is a breakpoint?
#### A breakpoint is an intentional stopping or pausing place in a program, put in place for debugging purposes. It is also sometimes simply referred to as a pause.More generally, a breakpoint is a means of acquiring knowledge about a program during its execution. During the interruption, the programmer inspects the test environment (general purpose registers, memory, logs, files, etc.) to find out whether the program is functioning as expected. In practice, a breakpoint consists of one or more conditions that determine when a program's execution should be interrupted.
## 6.What does the word ‘debugger’ do in your code?
#### The breakpoint can be achieved by putting a **debugger statement** in the code in the line you want to break. Many programming languages and software development tools also offer programs to aid in debugging, known as debuggers.

