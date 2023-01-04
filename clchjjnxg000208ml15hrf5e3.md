# Demystifying JSX

Manipulating the DOM using JavaScript is possible but very verbose.

The React library is written using JavaScript, and it does allow some reduction in the code. But still, it is not a good choice to try to emulate HTML code in JavaScript by using the built-in React functions like `createElement`, and so on.

Hence, JSX was born. It is allegedly an acronym of "JavaScript XML", which by itself is an acronym of "eXtensible Markup Language".

JSX is a syntax extension for JavaScript that allows you to write HTML-like code in your JavaScript code. It is often used with libraries like React to build user interfaces.  
Here is an example of JSX:

```javascript
const ele = <h1>Namaste JSX</h1>;
```

In this example, `ele` is a JSX element that represents an `h1` element. So when a JSX element is compiled, it is transformed into a JavaScript object that represents the DOM element.

Also if you `console.log(ele)` you will see that `ele` is an object. It doesn't directly become HTML. It becomes an object which is understood by React, which by itself updates the DOM using the information from that object.

JSX elements can also contain JavaScript expressions, which are evaluated and inserted into the JSX element at runtime. For example:

```javascript
const name = 'Albus'; 
const ele = <h1>Namaste, {name}!</h1>;
```

In this example, the JSX element is equivalent to the following JavaScript code:

```javascript
const ele = React.createElement('h1', {}, "Hello, " + name + "!");
```

JSX is not a part of the JavaScript language, so it must be transformed into JavaScript code in order to be used in a JavaScript application. This is typically done using a transpiler like Babel.

**JSX has many superpowers that make it a useful tool for building user interfaces:**

* Expressions: JSX allows you to write HTML-like code in your JavaScript, which can make it easier to understand and write UI code. This is instead of the verbose `React.createElement`.
    
* Performance: JSX is compiled by Babel to native JavaScript code, so it is as fast as writing raw JavaScript.
    
* Integration with React: JSX is often used with the React library, and it is designed to work with React. You can use JSX to manipulate the structure of a React component using just JavaScript, and React will efficiently update the DOM to match the structure of the JSX element without issues.
    
* Reusable components: You can use JSX to define reusable components that can be rendered in multiple places in your application. This can make it easier to build and maintain large applications.
    

**But...**

JSX has a few syntax rules that you need to follow, such as using camelCase for HTML attributes and specifying the class attribute as `className`. So, once you get used to these rules, `JSX` is very powerful.

But also, never confuse `JSX` with actual HTML. It is not HTML, it is "HTML-like".