# Reading React Reconciliation

Allow me to explain it as simply as I can. It is just matching or reconciling (fancier word for 'matching') the nodes in the Virtual DOM with the nodes to be added to it, before updating the actual DOM. This makes changing the virtual DOM that much faster, as the nodes that are to be updated carry with them their unique identifier.

These unique identifiers are called 'Keys' in React.

For React, "key reconciliation" means the process of matching elements in a list with their corresponding keys when the list is updated.

This is an important concept when working with lists of elements in React, as it allows React to efficiently update the list and minimize the number of DOM (Document Object Model) operations that are required.

In order to reconcile a list of elements in React, you need to specify a unique "key" for each element in the list. This key should be a stable identifier that does not change when the element is updated.

When the list is updated, React will use the keys to match the elements in the new list with the elements in the previous list, and will only update the elements that have changed.

Here's a simple example of key reconciliation in action:

```javascript
import React from 'react';

const List = ({ items }) =>(
    <ul>
    {items.map(item => (<li key={item.id}>{item.name}</li>))} 
    </ul>
);
```

In this example, we have a list of items that are rendered as a `ul` element with a series of `li` elements. Each `li` element has a unique key prop that is set to the id of the item. When the list is updated, React will use the id values to reconcile the elements in the list, and will only update the `li` elements that have changed.

Key reconciliation is an important concept in React, as it allows React to efficiently update lists of elements and minimize the number of DOM operations that are required. By using unique keys for each element in the list, you can ensure that React can efficiently update the list when it changes.

### There is also a question of using "index" as "Keys".

Using index numbers as keys in React can be a bad idea because keys are used to identify elements in a list, and index numbers can change when the list is updated. If you use index numbers as keys, React will not be able to efficiently update the list when it changes, as it will not be able to match the elements in the new list with the elements in the previous list.

Here's an example of why using index numbers as keys can be problematic:

```javascript
import React from 'react';

const List = ({ items }) =>(
    <ul> 
    {items.map((item, index) => (<li key={index}>{item.name}</li>))}
    </ul> 
);
```

In this example, we have a list of items that are rendered as a ul element with a series of li elements. Each li element has a key prop that is set to the index of the item in the list.

Suppose we have the following list of items:

```javascript
const items = [ 
    { name: 'Item 1' }, 
    { name: 'Item 2' }, 
    { name: 'Item 3' },
];
```

Now suppose we want to update the list by adding a new item at the beginning of the list, wanting the list to look like this:

```javascript
const items = [ 
    { name: 'Item 0' }, 
    { name: 'Item 1' }, 
    { name: 'Item 2' }, 
    { name: 'Item 3' },
];
```

If we render this updated list using the List component from the previous example, React will not be able to efficiently update the list, as it will not be able to match the elements in the new list with the elements in the previous list. This is because the index numbers of the elements have changed, and React will not be able to match the elements based on their index numbers alone.

As a result, React will have to rebuild the entire list, which is the entire purpose of making the virtual DOM do all work, which is now defeated. This is why it is generally a bad idea to use index numbers as keys in React.

It is still far superior to use index as "Keys" rather than not having Keys at all.

Instead, it is better to use a stable, unique identifier (key) for each element in the list as the key. This will allow React to efficiently update the list more efficiently.

It saves a lot of rerendering, and confusion about where an added element is situated among its siblings.