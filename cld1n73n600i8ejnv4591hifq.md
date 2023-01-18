# Optional Chaining in JavaScript

Developers love workflows. If something takes an hour to be done, but takes a day to be automated, developers will sell their souls to automate it. For such automation on a microscale, we have "optional chaining".

Optional chaining is a new syntactic sugar introduced in JavaScript (added in ECMAScript 2020) that allows you to access the properties of an object without having to check if the object or its parent objects are null or undefined.

For example, consider the following object:

```javascript
const obj = {
  a: {
    b: {
      c: 'hello',
    },
  },
};
```

To access the value of `c` using traditional JavaScript, you would have to check if each object in the chain is defined:

```javascript
let cVal;
if (obj && obj.a && obj.a.b) {
  cVal = obj.a.b.c;
}
```

With optional chaining, you can simply use the ?. operator to access the property:

```javascript
const cVal = obj?.a?.b?.c;
```

If any part of the chain is undefined or null, the whole expression will evaluate to `undefined`. So, it isn't true that there is no checking, but that the check is built into the syntax itself.

You can also use optional chaining to call a function on an object, if the object and the function both exist.

```javascript
const obj = {
  a: {
    b: {
      c: 'hello',
    },
  },
};
const cVal = obj?.a?.b?.c();
```

In the example above, if any of `obj`, `obj.a`, or `obj.a.b` are undefined, the entire expression will evaluate to undefined and the function `c` won't be called.

You can also use Optional Chaining to assign a value to a property.

```javascript
const obj = {};
obj?.a?.b = "hello";
console.log(obj);
```

In this example, `obj.a` will be created as an object, and inside it `obj.a.b` will be created the value of `b` will be set to `"hello"`.

In summary, optional chaining is a concise and efficient way to access the properties and methods of an object without having to check for null or undefined values at each step of the chain.