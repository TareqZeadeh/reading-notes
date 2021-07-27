# Forms in React App
### - In HTML, form elements such as (input) and (select) maintain their own state and update it based on user input.
### - On the other hand , In React, mutable state is kept in the state property of components, and only updated with setState().
### - controlled component is an input form element whose value is controlled by React in a way that combine the HTML form elements and the React mutable state's by making the React state be the “single source of truth”.
### The React component that renders a form also controls what happens in that form on subsequent user input. 

# The Conditional (Ternary) Operator 
## - Its mean that we can our if statment Shorter by writeing it in one but in easier different way .
### - For Example: 
### - The following syntax is a typical if statement:
```

if ( condition ) {
  value if true;
} else {
  value if false;
}

``` 

### - In the ternary operator , the above if statment syntax can be rewrote by the following way:
```

condition ? value if true : value if false

```

## Here’s what you need to know:
#### 1. The _condition_ is what you’re actually testing. The result of your condition should be _true_ or _false_ or at least coerce to either boolean value.
#### 2. A _?_ separates our conditional from our **true** value. Anything between the _?_ and the _:_ is what is executed if the _condition_ evaluates to **true**.
#### 3. Finally a _:_ colon. If your _condition_ evaluates to **false**, any code after the colon is executed.


