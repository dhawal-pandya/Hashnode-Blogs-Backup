# A fragment on React.Fragment

A "Fragment" is a part of a whole, in the context of coding, fragmenting is breaking, or rather compartmentalizing pieces of code that must not interfere with each other, but still are a part of the same whole.

In React, a fragment is a way to group a list of children without adding extra nodes to the DOM. Fragments are useful when you want to return multiple elements from a component's render method, but you don't want to wrap those elements in an extra element. Fragments are implemented as a special component called React.Fragment, which does not render any extra HTML elements in the DOM. Instead, it simply groups the children that are wrapped in it and returns them as a single unit.

When we import React in our .js file, Fragments are imported from the React js files, but it is not imported by default, hence we write "React.Fragment".

Let's see an example, suppose you have a component that renders a list of items.

Without fragments, you might write the following code:

```javascript
render() { 
    return ( 
        <div>
            <div className="Layer1">
                <div className="Layer2">
                    <div className="Layer3"></div>
                </div>
            </div>
        </div> 
    );
}
```

This works fine, but the problem is that the extra div element adds an unnecessary node to the DOM, which can hurt performance.

These extra divs coming from so many components result in what is known as a 'div soup', which is just the presence of unnecessary div in the node tree.

To avoid this, you can use a fragment to group the div components without adding an extra node:

```javascript
render() { 
    return ( 
        <React.Fragment>
            <div className="Layer1">
                <div className="Layer2">
                    <div className="Layer3"></div>
                </div>
            </div>
        </React.Fragment> 
    );
}
```

Alternatively, you can use the short syntax for fragments, which is just an empty pair of angle brackets `<>`.

It is just syntactic sugar meant to make the code less "ugly". They can help to keep your DOM structure clean and simple, and can make it easier to work with lists of elements in React.

```javascript
render() { 
    return ( 
        <>
            <div className="Layer1">
                <div className="Layer2">
                    <div className="Layer3"></div>
                </div>
            </div>
        </> 
    );
}
```

So Beautiful!!!