# Mapping .map files

You've seen them in some folders, but just ignored them, because things just worked without you knowing about it. But not anymore. *We gonna learn today!*

In a Parcel React app, the "dist" folder (short for "distribution") typically contains the built version of your app, which is the code that will be served to users when they access your app.

The "map" files in the "dist" folder are source map files, which are used to map the built code, back to the original source code.

Source maps are useful for debugging as they allow you to see the original source code, even when you are working with the built version of the code.

When you view the built code in a browser, the source map will be used to map the built code back to the original source code, so you can see the original line numbers, file names, and other debugging information.

There are typically multiple "map" files in the "dist" folder, one for each JavaScript file in your app. These files are typically named after the corresponding JavaScript file, with a ".map" extension. For example, if you have a JavaScript file named "main.js" in your "dist" folder, you might also see a "main.js.map" file.

In a Parcel React app, the "map" files in the "dist" folder are generated automatically by Parcel as part of the build process.

You should not need to modify these files manually, but they can be useful for debugging if you need to understand how the built code maps onto the original source code.

### How do the .map files work though?

Source map files work by providing a mapping between the built code and the original source code.

Here's a simplified version of how a source map might work:

1. You write some JavaScript code and save it in a file called "main.js".
    
2. You run the code through a build process, which minifies the code and generates a corresponding source map file called "main.js.map".
    
3. You deploy the built code, "main.js", and the source map, "main.js.map", to a web server.
    
4. A user accesses your app in their browser, and the browser downloads the built code, "main.js".
    
5. The browser sees that there is a corresponding source map file, "main.js.map", and downloads it as well.
    
6. When the user opens the developer console and clicks on a line of the built code, the browser uses the source map to map the line of built code back to the original line of code in the source file, "main.js".
    

This allows the user to see the original line numbers, file names, and other debugging information, even when working with the built code.

Generally, source maps are a useful tool for debugging and troubleshooting, as they allow you to see the original source code, even when you are working with the built version of the code. They are particularly useful for debugging minified code, as minification can make the code difficult to read and understand.