# What are Node Modules?

`node_modules` is a directory that is created when you install packages in your project using a package manager like npm or yarn. The directory contains the packages and their dependencies, as well as any other files that are needed by the packages.

For example, if you install a package called my-package in your project using npm, it will be placed in the node\_modules directory, along with any other dependencies that my-package requires. The directory structure might look something like this:

```plaintext
node_modules
├── my-package
│ ├── package.json
│ ├── index.js
│ ├── ...
├── dep1
│ ├── package.json
│ ├── index.js
│ ├── ...
├── dep2
│ ├── package.json
│ ├── index.js
│ ├── ...
└── ...
```

Here, the `node_modules` directory contains the my-package package, as well as its dependencies dep1 and dep2. Each package has its own package.json file and other necessary files.

Also do not forget to add `node-modules` to your `gitignore` files, otherwise it will make your repository heavier than a small planet. It can be safely generated on the server, and it is never to be modified.