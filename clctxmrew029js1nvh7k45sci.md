# Demystifying Polyfills

Coming from the product of "Polyfillia", which is a paste used by civil engineers to fill cracks and holes in an otherwise useable wall, we have a "Polyfill", which seals and fills the holes of old browsers not understanding newer code.

So, Polyfills are pieces of code that add new functionality to a web browser, allowing it to support features that it does not natively support. They are often used to enable new features in older browsers that do not support the latest web standards or to provide consistent behavior across different browsers.

For example, suppose a new web standard is developed that introduces a new HTML element called "my-element". This element might be supported by the latest version of a particular web browser, but older versions of the same browser might not support it. In this case, a polyfill could be used to add support for "my-element" to the older versions of the browser, allowing developers to use the new element in their web pages.

Polyfills are usually implemented in JavaScript and can be included in a web page through a script tag. They are often used to enable new features that are not yet widely supported by browsers, or to ensure that a web page behaves consistently across different browsers.

What smart developers do is mimic the behavior of newer types of code using the older versions of the code. For example, the `.map` function may not be supported by older versions of browsers, so the developers write a new function...

```javascript
function myMap () {...} 
```

and that is called wherever `.map` is called.

In general, polyfills are useful for enabling new web standards and features in older browsers, and for providing consistent behavior across different browsers. They can help to ensure that web pages and applications can take advantage of the latest web technologies, even if some users are using older or less capable browsers, which would be a shame.

So polyfills are just pieces of code ultimately, as we all are.