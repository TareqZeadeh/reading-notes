# Thinking in React
## One of the many great parts of React is how it makes you think about apps as you build them.
## If we already have a JSON API and a mock from our designer, The process of building a searchable product data table using React will be in 5 Steps:
### *step 1: Break The UI Into A Component Hierarchy.
#### _The first thing you’ll want to do is to draw boxes around every component (and subcomponent) in the mock and give them all names. 

#### _IN order to know what should be its own component or deciding if you should create a new function or object there is technique thats called the **single responsibility principle**, that is, a component should ideally only do one thing. If it ends up growing, it should be decomposed into smaller subcomponents.
#### _Since you’re often displaying a JSON data model to a user, you’ll find that if your model was built correctly, your UI (and therefore your component structure) will map nicely. That’s because UI and data models tend to adhere to the same information architecture. Separate your UI into components, where each component matches one piece of your data model.
### *Step 2: Build A Static Version in React.
#### -Now that you have your component hierarchy, it’s time to implement your app. The easiest way is to build a version that takes your data model and renders the UI but has no interactivity. It’s best to decouple these processes because building a static version requires a lot of typing and no thinking, and adding interactivity requires a lot of thinking and not a lot of typing.
#### -To build a static version of your app that renders your data model, you’ll want to build components that reuse other components and pass data using props. props are a way of passing data from parent to child. If you’re familiar with the concept of state, don’t use state at all to build this static version. State is reserved only for interactivity, that is, data that changes over time. Since this is a static version of the app, you don’t need it.
#### -You can build top-down or bottom-up,ou can either start with building the components higher up in the hierarchy (i.e. starting with FilterableProductTable) or with the ones lower in it (ProductRow).
#### -At the end of this step, you’ll have a library of reusable components that render your data model.
### *Step 3: Identify The Minimal (but complete) Representation Of UI State.
#### - To make your UI interactive, you need to be able to trigger changes to your underlying data model. React achieves this with _state_.
#### -To build your app correctly, you first need to think of the minimal set of mutable state that your app needs. The key here is DRY: Don’t Repeat Yourself. Figure out the absolute minimal representation of the state your application needs and compute everything else you need on-demand.
### *Step 4: Identify Where Your State Should Live
#### -Remember: React is all about one-way data flow down the component hierarchy. It may not be immediately clear which component should own what state.
### *Step 5: Add Inverse Data Flow.
#### -To support data flowing the other way you should pass callbacks that will fire whenever the state should be updated,you can use the _onChange event_ on the inputs to be notified of it.