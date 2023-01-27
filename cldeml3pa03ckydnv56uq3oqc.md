# What is a Pure Function?

In computer science, a pure function is a function that, given the same input, will always return the same output and have no side effects. They do not modify the state of the system or have any observable side effects such as network or database calls.

You know you've encountered or unintentionally written a pure function when:

* It always returns the same output for the same input
    
* It does not have any side effects (e.g. modifying the global state, making network or database calls).
    
* It does not depend on the state of the system or any global variables
    

Good examples of pure functions are mathematical functions like sin(x) and cos(x), where the output is determined solely by the input and the function's algorithm.

On the other hand, an impure function is a function that has side effects and its output may not always be the same for the same input. They may modify the state of the system or have observable side effects such as network or database calls.

Bad examples of pure functions or good examples of impure functions can be fetching data from a server, updating a global variable, or modifying the state of an object.

For example, this function is a pure function because it always returns the same output for the same input and does not have any side effects:

```javascript
const add = (a, b) => a + b
```

On the other hand, this function is an impure function because it modifies the global state and its output may not always be the same for the same input:

```javascript
let counter = 0;
const incrementCounter = () => { 
    counter++; 
    return counter;
}
```

### In React JS

In React, pure functions are preferred in components as they are more predictable, easier to test and debug, and can help improve performance.

It is recommended to use pure functions as much as possible in React, particularly in the render method and hooks, in order to avoid unexpected behavior and to keep the state of the component predictable and easy to understand.

Additionally, using pure functions in the render method and hooks can also improve the performance of the application, as React can use the output of the pure functions to determine when to update the component.

For example, when using useEffect hook in React, it's recommended to pass a pure function as the callback so that React can compare the values of the dependencies and determine when to call the effect callback again, not even an async pure function.

In general, it's always a good practice to use pure functions as much as possible in your application. They are more predictable, easy to test, and can improve performance. However, it's important to understand when impure functions are necessary, such as when making network or database calls, and to use them in a controlled and predictable way.