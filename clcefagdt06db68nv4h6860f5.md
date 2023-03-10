# Parcel vs Webpack

Parcel and Webpack are like the duct tape of the JavaScript world. They take all of your messy, disorganized code and bundle it up nicely, so it's easy to transport and use in other projects, called 'Bundlers'.

### Why do we use Bundlers?

**Modularity**  
In a large JavaScript project, it is common to split the code up into multiple files for easier maintenance and debugging. But, when it comes time to deploy the code, it is often more convenient to have all of the code in a few files.

A JavaScript bundler can take all of the separate files and combine them into a single file, making it easier to deploy.

**Performance**  
A JavaScript bundler can also optimize your code to make it run faster in the browser. Minification and Tree Shaking are the ways the bundlers do it.

**Advanced features**  
JavaScript bundlers can also provide several advanced features, such as supporting pre-processors like Sass or TypeScript, code splitting, or even just 'lazy loading', which allows you to load code on demand, rather than all at once. It truly is brilliant what engineering we come up with.

### Webpack

Webpack is one of the JavaScript bundlers that is widely used to build and deploy modern web applications. It is a powerful tool that can take your JavaScript code, along with all of its dependencies, and package it up into a few files that can run in a web browser.

One of the key reasons Webpack being so good is its ability to split your code up into small chunks, called "modules," that can be loaded on demand. This is known as `code splitting`, which allows you to load only the code that is needed for a particular page or feature, rather than loading all of the code at once, improving the performance of your application by reducing the amount of code that needs to be downloaded and executed by the browser at a time.

Webpack also has many other advanced features, like supporting pre-processors, like Sass or TypeScript, and the ability to transform code using tools like **Babel** *(which allows you to use modern JavaScript syntax even if it is not supported by all browsers)* and **PostCSS** *(which allows you to use advanced CSS features that may not be supported by all browsers)*.

Webpack is highly configurable and it can be customized to fit the specific needs of a project. Therefore, it is often used on larger and more complex projects that require a more advanced build and deployment processes.

### Parcel

> "Parcel is a 'Beast'". -Akshay Saini, 2022.

Parcel is another JavaScript bundler that is inherently designed to be easy to use and requires very little configuration. This tool can take your JavaScript code, along with all of its dependencies, and package it up into a few files that can be run in a web browser, very similar to Webpack.

One of the distinguishing features of Parcel is its ability to automatically detect and process a wide variety of files, such as JavaScript, CSS, HTML, and images. Meaning you don't have to manually configure Parcel to handle these types of assets, it will just work.

Parcel also transforms code using tools like **Babel** *(which allows you to use modern JavaScript syntax even if it is not supported by all browsers)* and **PostCSS** *(which allows you to use advanced CSS features that may not be supported by all browsers)*.

In addition to its ease of use and asset processing superpowers, Parcel is also known for its performance. It uses various optimization techniques, such as "minification" *(which removes unnecessary whitespace and comments and* `console.log`*s from the code)* and "tree shaking" *(which eliminates unused code)*, to ensure that the bundled code runs as efficiently as possible in the browser, by being the most compact as possible.

Parcel is an obvious choice for an easy-to-use and efficient JavaScript bundler. It is especially well-suited for smaller projects or projects that don't require a lot of customization.

### Differences between Parcel and Webpack

**Configuration**  
One of the main differences between Parcel and Webpack is the amount of configuration required to get started. Parcel is designed to be easy to use and requires minimal configuration.

```bash
npx parcel entryPoint.js -y
```

You can simply point it at your entry point JavaScript file like this, and it will automatically process all of the dependencies and assets needed by your project.

Webpack requires more configuration to get started. You will need to create a configuration file (usually called "webpack.config.js") that specifies the entry point for your project and defines any additional settings or options you want to use.

**Asset processing**  
Both Parcel and Webpack automatically detect and process a wide variety of assets.

However, Parcel is generally considered to be easier to use and requires less configuration for it. It can detect and process most types of assets, and it also transforms code using tools like Babel and PostCSS without any additional configuration.

Webpack requires additional configuration to process different types of assets, and it may even require the use of loaders or plugins to transform code.

**Performance**

Both Parcel and Webpack offer optimization techniques, such as minification and tree shaking, to ensure that the bundled code runs efficiently in the browser.

Admittedly though, Webpack is considered to be more powerful and flexible when it comes to optimizing code, but at the cost of more configuration to get the best performance. Webpack allows you to define specific optimization techniques and settings in the config file.

While Parcel uses a set of default optimization techniques that are applied automatically, which also means that you cannot really decide what and how to optimize.

**Code splitting**

Webpack includes the ability to split your code into small chunks, called "modules," that can be loaded on demand, which is known as code splitting. This can improve the performance of your application by reducing the amount of code that needs to be downloaded and executed by the browser at a time.

Parcel does not have built-in support for code splitting, but it can be achieved using plugins, which are just extra steps we want to avoid by choosing Parcel.

So basically, Parcel for smaller or less config-hungry applications, and Webpack for bigger and more complex apps are the better choices.