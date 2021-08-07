# React Docs - lists and keys
## 1.What does .map() return?
#### Its returns a new array with the modified Data.
## 2.If I want to loop through an array and display each value in JSX, how do I do that in React?
#### We can use map() method in order to loop through the givin array .
#### To display each value in the array in JSX we need to use **(ReactDOM.render())**.
##### EX:
```
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li>{number}</li>
);
ReactDOM.render(
  <ul>{listItems}</ul>,
  document.getElementById('root')
);
```

## 3.Each list item needs a unique __Key__.
## 4. What is the purpose of a key?
#### Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity.
# =====================================================================================================
# =====================================================================================================
# How to Use the Spread Operator (…) in JavaScript
## 1.What is the spread operator?
#### In JavaScript, spread syntax refers to the use of an ellipsis of three dots (…) to expand an iterable object into the list of arguments.
## 2.List 4 things that the spread operator can do.
#### 1.Spreads the array into separate arguments.
#### 2.Copying an array.
#### 3.Concatenating or combining arrays.
#### 4.Using Math functions.
#### 5.Using an array as arguments.
#### 6.Adding an item to a list.
#### 7.Adding to state in React.
#### 8.Combining objects.
#### 9.Converting NodeList to an array.
## 3.Give an example of using the spread operator to combine two arrays.
```
const myArray = [`🤪`,`🐻`,`🎌`]
const yourArray = [`🙂`,`🤗`,`🤩`]
const ourArray = [...myArray,...yourArray]
console.log(...ourArray) // 🤪 🐻 🎌 🙂 🤗 🤩

```


## 4.Give an example of using the spread operator to add a new item to an array.
```
const fewFruit = ['🍏','🍊','🍌']
const fewMoreFruit = ['🍉', '🍍', ...fewFruit]
console.log(fewMoreFruit) //  Array(5) [ "🍉", "🍍", "🍏", "🍊", "🍌" ]

```

## 5.Give an example of using the spread operator to combine two objects into one.
```
const objectOne = {hello: "🤪"}
const objectTwo = {world: "🐻"}
const objectThree = {...objectOne, ...objectTwo, laugh: "😂"}
console.log(objectThree) // Object { hello: "🤪", world: "🐻", laugh: "😂" }
const objectFour = {...objectOne, ...objectTwo, laugh: () => {console.log("😂".repeat(5))}}
objectFour.laugh() // 😂😂😂😂😂

```
# ============================================================================================
# ============================================================================================
# How to Pass Functions Between Components.
## 1. In the video, what is the first step that the developer does to pass functions between components?
#### Passing the function as an attribut to the child component, thin in the child component he use **props** in order to be able to call the function.
## 2. In your own words, what does the **increment** function do?
#### Increasing the count propraprity in the object that its name propraprity matched the paased name in the _people array of objects_.
## 3. How can you pass a method from a parent component into a child component?
#### By passing the function as an attribut to the child component in the **component tag**, thin in the child component he use **props** in order to be able to call the function.
## 4. How does the child component invoke a method that was passed to it from a parent component?
#### using the **props** , For Example: this.props.the name of the attribut that holding the method () 