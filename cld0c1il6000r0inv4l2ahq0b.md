# useState() and useEffect()

React hooks are a new feature in React that was introduced in React 16.8. They allow you to use state and other React features without writing a class. This makes it easy to share stateful logic between components and can make function components as powerful as class-based components.

There are two main types of hooks: state hooks and effect hooks. If you know these hooks most of the others are mere approximations or sugars for these ones.

### useState()

useState is a state hook, unbelievably. It allows you to manage state in functional components. They are used like this:

```javascript
import { useState } from 'react';

const Counter = () => {
    const [count, setCount] = useState(0);
    return (
        <div>
            <p>You clicked {count} times</p>
            <button onClick={() => setCount(count + 1)}>
            Click me
            </button>
        </div>
    );
};
```

The useState hook takes a single argument, which is the initial state. It returns an array with two elements: the current state and a function to update the state. In the example above, `count` is the current state, and `setCount` is a function that updates the state.

You need them because if you write variable and use them without states, then the Reconciliation engine will just overwrite it.

### useEffect()

Also unbelievably, useEffect is an effect hook, which allows you to perform side effects in function components. They are used like this:

```javascript
import { useEffect } from 'react';

const Awesome = () => {
    useEffect(() => {
        console.log('I am an effect!');
        return () => console.log('I am a cleanup function!');
        });
    return <div>I am a component</div>;
}
```

The `useEffect` hook takes a function as an argument. This function is called an effect, and it is run after the component renders. The effect can perform any side effects, such as making a network request or subscribing to an event.

The `useEffect` hook can also accept a second argument, which is an array of dependencies. If the array is empty, the effect will only run once, when the component mounts. If the array contains values, the effect will run every time one of those values changes.

The useEffect hook is a way to add side effects to your React components.

A "side effect" is any behavior that affects the component or the application outside of the component's render method. Some examples of side effects include fetching data from a server, setting up a subscription, or updating the document title even.

The useEffect hook is called after the component has rendered and it takes two arguments: a function that contains the side effect code and a list of dependencies.

```javascript
useEffect(() => {}, [dependencies])
```

The function passed to useEffect is called an effect. It is called immediately after the component is rendered, and also after every re-render if the dependencies haven't changed.

The list of dependencies is an array of values that the effect depends on. If any of the dependencies change, the effect will be called again. If you pass an empty array as the second argument, the effect will only be called once, after the initial render.

The useEffect hook can even be used to have the side effect of fetching data from a server.

```javascript
import { useState, useEffect } from 'react';
function MyComponent(props) {
    const [data, setData] = useState(null);
    useEffect(() => {fetch('https://my-api.com/data').then(response => response.json()).then(data => {setData(data);
        });
    }, []); 
// passing empty array as second argument
    if (!data) {
    return <div>Loading...</div>;
    }
    return <div>{data.message}</div>;
};
```

In this example, the effect is a call to the fetch function, which retrieves data from a server and stores it in the data state. Since we passed an empty array as the second argument, the effect will only be called once, after the initial render.

It's worth noting that useEffect is a powerful hook that can be used for different purposes, it can be used to handle subscriptions, interact with browser APIs and much more, with the right usage it can make your components more powerful and flexible.

### Mistakes on useEffect:

`useEffect` is a Hook in React that allows you to synchronize a component with an external system. It is commonly used for fetching data, setting up subscriptions, and updating the DOM in response to a prop or state change.

Also, it is very difficult to grasp at first.

Here are some common mistakes made when using `useEffect` and how to solve them:

1. **Not including dependencies in the dependency array**: If you forget to include a dependency in the dependency array, the effect will run on every render and might go apeshit. To solve this, make sure to include all the variables that the effect depends on in the dependency array if that apeshit behavior is not the intention.
    
2. **Including unnecessary dependencies in the dependency array**: Including unnecessary dependencies in the dependency array will cause the effect to re-run more often than it needs to. To solve this, make sure to only include the variables that the effect actually needs to run.
    
3. **Not cleaning up an effect**: If an effect sets up a subscription or a timer, it should also clean up that subscription or timer when the component unmounts or the effect re-runs. To solve this, return a cleanup function from the effect that undoes the setup. A clean-up function is a function that is returned at the end of the useEffect function signifying that the side-effect has ended.
    
4. **Not handling an effect's cleanup correctly**: Returning the cleanup function from the effect is not enough, it also needs to be passed to `useEffect` as a second parameter. To solve this, make sure to pass the cleanup function as the second parameter to `useEffect` so that it gets called when the component unmounts or the effect re-runs.
    
5. **Not handling an effect's errors**: Effects can throw errors, but they don't have a try-catch block. To solve this, you can use `try-catch` block inside your function or use `useEffect` with an empty dependency array and handle the errors like a pro React dev.
    

In summary, using `useEffect` correctly requires paying attention to the dependencies, cleanup, and order of execution. It's important to understand the trade-offs of when to use `useEffect` and how to handle its errors.

React hooks are overall a powerful new feature that can make your code simpler and more reusable. They are easy to learn and use, and they can help you write better React applications.