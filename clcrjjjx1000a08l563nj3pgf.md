# What is Virtual DOM?

Unlike your digital fetishes, virtual DOM (Document Object Model) is a lightweight in-memory 'representation of a DOM' tree.

It is a programming interface that abstracts away the details of the actual DOM, and allows developers to manipulate the DOM indirectly by interacting with the virtual DOM instead.

When you update a component in a React app, the virtual DOM creates a new virtual tree that represents the updated component. It then compares this virtual tree to the previous virtual tree and calculates the minimum number of changes that need to be made to the actual DOM to bring it into line with the updated virtual tree.

Once the virtual DOM has calculated the necessary changes, it sends them to the browser, which updates the actual DOM to reflect the changes. This process is known as "reconciliation" (matching, reconciling the virtual DOM and actual DOM), and it is what allows React to efficiently update the DOM in response to changes in the component tree. This is what makes React so fast.

By using the virtual DOM, React is able to minimize the number of DOM operations that are required when updating the DOM, which can help to improve the performance of the app.

Here's a simplified example of how the virtual DOM works in React:

\- A component is rendered to the virtual DOM.

\- The component is updated, and the virtual DOM creates a new virtual tree that represents the updated component.

\- The virtual DOM compares the new virtual tree to the previous virtual tree and calculates the minimum number of changes that need to be made to the actual DOM.

\- The virtual DOM sends the necessary changes to the browser, which updates the actual DOM to reflect the changes.

So, now you know you can always trust your DOM.