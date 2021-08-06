# Concepts of Functional Programming in Javascript.
## 1.What is functional programming?
#### Functional programming (often abbreviated FP) is the process of building software by composing pure functions, avoiding shared state, mutable data, and side-effects. Functional programming is declarative rather than imperative, and application state flows through pure functions. Contrast with object oriented programming, where application state is usually shared and colocated with methods in objects.
## 2.What is a pure function and how do we know if something is a pure function?
#### Pure functions are the atomic building blocks in functional programming. They are adored for their simplicity and testability.
##### A function must pass two tests to be considered “pure”:
###### 1. Same inputs always return same outputs.
###### 2. No side-effects.
## 3.What are the benefits of a pure function?
#### 1.They’re easier to reason about.
#### 2.They’re easier to combine.
#### 3.They’re easier to test.
#### 4.They’re easier to debug.
#### 5.They’re easier to parallelize.
#### 6.They are idempotent.
#### 7.They offer referential transparency.
#### 8.They are memoizable.
#### 9.They can be lazy.
## 4.What is immutability?
#### Unchanging over time or unable to be changed.
#### When data is immutable, its state cannot change after it’s created. If you want to change an immutable object, you can’t. Instead, you create a new object with the new value.
## 5.What is Referential transparency?
#### Referential transparency is an oft-touted property of (pure) functional languages, which makes it easier to reason about the behavior of programs. While there is no single formal definition, it usually means that an expression always evaluates to the same result in any context. Side effects like (uncontrolled) imperative update break this desirable property. C and ML are languages with constructs that are not referentially transparent.
##### **Simply**, Referential transparency is a term you’ll hear a lot in functional programming. It means that an expression can be replaced by its result. That is, 5+4 can be replaced by 9, without changing the behavior of the program. You can extend the definition also to functions. So you can say + is referentially transparent, because if you call it with the same values, it will give you the same answer.
# ==================================================================================
# ==================================================================================
# Node JS Tutorial for Beginners #6 - Modules and require()
## 1.What is a module?
#### Module is a JS file which will hold a functional part of an application code so we can reuse it whenever we want.
## 2.What does the word ‘require’ do?
#### require() is used to consume modules. It allows you to include modules in your app. You can add built-in core Node.js modules, community-based modules (node_modules), and local modules too.
#### Node.js follows the CommonJS module system, and the **built-in require function** is the easiest way to include modules that exist in separate files. The basic functionality of **require** is that it reads a JavaScript file, executes the file, and then proceeds to return the exports object.
## 3.How do we bring another module into the file the we are working in?
##### Using **require()** mathod and attach with it the path of the file that we want. 
## 4.What do we have to do to make a module available?
#### In Node.js, each module has its own scope. A module cannot directly access things defined in another module unless it chooses to expose them. To expose things from a module, they must be assigned to exports or module.exports. For a module to access another module's exports or module.exports, it must use require().
