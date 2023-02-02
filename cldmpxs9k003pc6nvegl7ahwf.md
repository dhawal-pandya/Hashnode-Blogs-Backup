# Suspense and Lazy in React

Jest aside, and Jest as a testing mechanism aside as well, `React.lazy` and `Suspense` are two features in React that allow you to load components lazily, i.e. only when they are needed, instead of loading all components up front. This can improve the initial load time of your application and improve the overall user experience.

Here's how you can use `React.lazy` and `Suspense` in your React application:

```javascript
import React, { lazy, Suspense } from 'react';

const LazyComponent = lazy(() => import('./LazyComponent'));
const App = () => { 
    return ( 
    <div>
      <Suspense fallback={"Loading Component..."}>
       <LazyComponent />
      </Suspense>
    </div>
  );
}
export default App;
```

Here, the `LazyComponent` is defined as a lazy component using the `React.lazy` function. The `React.lazy` function takes a factory function as an argument that returns the component that you want to load lazily.

In this case, the component is imported using the import statement.

The `LazyComponent` is then wrapped inside a `Suspense` component. The `Suspense` component allows you to specify a fallback component that will be displayed while the lazy component is being loaded. This fallback is rendered while loading the component.

In this case, the fallback is a simple "Loading Component..." message.

When the `App` component is rendered, the `LazyComponent` will not be loaded until it is actually needed. This can improve the initial load time of your application and provide a better UX, as the user will only have to wait for the necessary components to load, rather than all components up front.

Once the `LazyComponent` has been loaded, it will be cached and will not need to be loaded again, unless it is unloaded from the cache. This helps to improve the overall performance of your application.

It's also worth noting that the `React.lazy` and `Suspense` features are designed to work with a code-splitting library, such as Webpack. Code-splitting allows you to break up your application into smaller chunks that can be loaded on demand, improving the overall performance of your application.

By using `React.lazy` and `Suspense` in combination with code-splitting, you can create an efficient and optimized React application that provides a better UX.

So basically, `React.lazy` and `Suspense` are awesome features that allow you to improve the performance and user experience of your React applications by loading components lazily and displaying fallback content while the components are being loaded. If you're not using these features yet, it's definitely worth taking the time to learn about them and implement them in your own projects.