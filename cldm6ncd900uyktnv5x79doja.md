# Code-Splitting in JavaScript

It is not you deleting huge sections of your code when you don't understand where the error is arising from.

No, code-splitting is a technique for dividing a large codebase into smaller, more manageable chunks or "bundles". Each bundle can be loaded on demand, reducing the amount of code that needs to be loaded at the start of the application, and improving the overall performance of the application.

### Why?

Code-splitting patterns are an important aspect of modern web development because they help improve the performance and user experience of web applications. By breaking down large codebases into smaller, more manageable chunks, code splitting patterns allow developers to:

* Improve initial load time: By loading only the code that is required for a specific route or component, code splitting patterns can reduce the amount of code that needs to be loaded at the start of the application, improving the initial load time.
    
* Speed up navigation: By loading code on demand, code splitting patterns can help speed up navigation within an application, making it feel more responsive and faster.
    
* Save on bandwidth costs: By only loading the code that is required, code splitting patterns can save on bandwidth costs, especially for mobile users who have limited data plans.
    
* Maintain codebase: Code splitting patterns help keep codebases organized and maintainable by breaking down large codebases into smaller, more manageable chunks.
    
* Improve scalability: By breaking down code into smaller, reusable chunks, code-splitting patterns make it easier to scale applications and add new features.
    

### How?

There are several approaches to code-splitting in JavaScript, including:

* Entry point splitting: Dividing your code into multiple entry points, each of which corresponds to a separate bundle.
    
* Route-based splitting: Dividing your code into separate bundles for each route or page in your application.
    
* Component-based splitting: Dividing your code into separate bundles for each component in your application.
    

### In React

In React, code-splitting can be done using the `React.lazy` and `Suspense` features, in combination with a code-splitting library such as Webpack.

### Conclusion

So basically, code splitting patterns are an essential aspect of modern web development that can help improve the performance, scalability, and maintainability of web applications. By breaking down large codebases into smaller, more manageable chunks, code-splitting patterns can help make your web applications faster, more responsive, and easier to maintain.

And if by chance you make them too fast, there's always:

```bash
npm i thanos-js
```