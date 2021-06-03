# Error Handling And Debugging
### -Order of Exscution :To find the source of an error, it helps to know how scripts are processed. The order in which statements are executed can be complex; some tasks cannot complete until another statement or function has been run.
### -Execution Contexts :The JavaScript interpreter uses the concept of execution contexts. There is one global execution context; plus, each function creates a new new execution context. They correspond to variable scope.
#### Every statement in a script lives in one of three execution contexts:
1. Global context:  Code that is in the script, but not in a function. There is only one global context in any page.
2. Function context : Code that is being run within a function. Each function has its own function context.
3. Eval context (not shown) Text is executed like code in an internal function called eval().
### -The Stack :  The JavaScript interpreter processes one line of code at a time. When a statement needs data from another function, it stacks (or piles) the new function on top of the current task.
### -Each time a script enters a new execution context, there are two phases of activity:
#### 1. Prepare 
1. The new scope is created.
2. Variables, functions, and arguments are created.
3. The value of the this keyword is determined. 
#### 2. Execute
1. Now it can assign values to variables
2. Reference functions and run their code
3. Execute statements
### -Understanding Scope: In the interpreter, each execution context has its own va ri ables object. It holds the variables, functions, and parameters available within it. Each execution context can also access its parent's v a ri ables object.
### -Understanding Errors: If a JavaScript statement generates an error, then it throws an **exception**. At that point, the interpreter stops and looks for exception-handling code.
### -Error objects: Error objects can help you find where your mistakes are and browsers have tools to help you read them.(look at page 466 in [js](https://drive.google.com/file/d/1L74jU_Js5jSjbi2hg87TNyT-hnVkoXwJ/view).)
### -Error objects Continued: look at page 467-468 in [js](https://drive.google.com/file/d/1L74jU_Js5jSjbi2hg87TNyT-hnVkoXwJ/view).
### -How to deal with errors: Now that you know what an error is and how the browser treats them, there are two things you can do with the errors.
1. Debug the script to fix errors.
2. Handle errors gracefully.
### -A Debugging workflow: Debugging is about deduction: eliminating potential causes of an error. Here is a workflow for techniques you will meet over the next 20 pages. Try to narrow down where the problem might be, then look for clues.

### -for more details, look at page 471-493 in [js](https://drive.google.com/file/d/1L74jU_Js5jSjbi2hg87TNyT-hnVkoXwJ/view).