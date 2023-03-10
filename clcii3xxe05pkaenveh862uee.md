# Tree-Shaking a Library.

What a weird title, if you do not have a CS background, those words make less sense when you think about shaking trees in a library. But to be honest, reading books, which are made of paper, which in turn are made of trees, and turning pages, essentially shaking them back and forth, in a library is not foreign anymore, is it?

Anyway, 'Tree shaking' is a term that is used in the context of JavaScript bundlers, such as Parcel and Webpack, to describe the process of eliminating unused code from the final bundle. It is a way to reduce the size and increase the performance of your web applications by only including the code that is actually being used in the final bundle.

For example, consider a project that has the following dependencies:

```json
dependencies: {
    "dep1": "^87.7.5",
    "dep2": "^2.24.3"
}
```

The project is using both the `dep1` and `dep2` libraries, but it is only using a small subset of the functions provided by each library. Without tree shaking, the bundler would include the entire `dep1` and `dep2` libraries in the final bundle, even though much of the code is not being used. This can significantly increase the size of the bundle and negatively impact the performance of the application.

To perform tree shaking, the bundler will analyze the code in your project to determine which parts of the `dep1` and `dep2` libraries are actually being used. It will then eliminate any code that is not being used, and only include the necessary code in the final bundle. For example, if the project is only using the `fn1` and `fn2` functions from `dep1`, the bundler will only include those functions in the final bundle.

Here is an example of what the final bundle might look like after tree shaking has been applied:

```json
bundle.js: {
    "dep1": {
        "fn1": [Function],
        "fn1": [Function]
    },
    "dep2": {
        "fn3": [Function]
    }
}
```

As you can see, the final bundle includes only the `fn1`, `fn2` and `fn3` functions from `dep1` and `dep2`, rather than the entire library. This can significantly reduce the size of the final bundle and improve the performance of the application.

All the cool people 'shake the tree', ***#ifykwim***