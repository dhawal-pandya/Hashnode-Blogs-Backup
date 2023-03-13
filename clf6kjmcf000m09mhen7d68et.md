---
title: "Let's build a Collapsible Accordion"
datePublished: Mon Mar 13 2023 08:34:45 GMT+0000 (Coordinated Universal Time)
cuid: clf6kjmcf000m09mhen7d68et
slug: lets-build-a-collapsible-accordion
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/RLHtsH4_Blw/upload/f4fdb2f0a0d9fc37b0de4f7fc2030535.jpeg
tags: javascript, reactjs, components, react-hooks, accordion

---

Let's build a collapsible accordion in ReactJS.

Accordions are a great way to display a large amount of content in a limited space. They allow the user to show and hide content by clicking on the header of each section. In this article, we will be creating a collapsible accordion component in React.

### Getting Started

Before we start building our component, we need to create a new React project. You can use create-react-app to quickly set up a new project.

```bash
npx create-react-app my-accordioncd my-accordion
```

```bash
npm start
```

### Creating the Component

Now that we have our project set up, we can create our collapsible accordion component.

Let's create a new file called Accordion.js in the src directory and add the following code:

```javascript
import React, { useState } from "react";
const Accordion = ({ title, children }) => {
    const [isOpen, setIsOpen] = useState(false);
    return (
        <div>
            <h3 onClick={() => setIsOpen(!isOpen)}>{title}{isOpen ? "-" : "+"}</h3>
            {isOpen && <div>{children}</div>}
        </div>
    );
};
export default Accordion;
```

In the code above, we are using the `useState` hook to manage the state of our accordion. The state determines whether the accordion is open or closed. We also added an onClick handler to the title of the accordion that toggles the state between open and closed.

### Using the Component

Now that we have our Accordion component, we can use it in our App.js file. Let's add the following code to App.js:

```javascript
import React from "react";
import Accordion from "./Accordion";

const App = () => {
    return (
        <div>
            <Accordion title="Section 1">
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing
                   elit. Nullamtincidunt velit vel nisl tempor, eget
                   congue nisl viverra.</p>
            </Accordion>
            <Accordion title="Section 2">
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing
                   elit. Nullamtincidunt velit vel nisl tempor, eget
                   congue nisl viverra.</p>
            </Accordion>
            <Accordion title="Section 3">
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing
                   elit. Nullamtincidunt velit vel nisl tempor, eget
                   congue nisl viverra.</p>
            </Accordion>
        </div>
    );
};

export default App;
```

In the code above, we are using the Accordion component three times to create three sections in our accordion. You can add as many sections as you need by simply duplicating the Accordion component.

### Creating a Multiple Accordion

In a scenario where you want to have multiple accordions and you want only one to be open at a time, you can use a shared state that is managed by a parent component.

Let's modify our Accordion component to receive the `openIndex` state from its parent component:

```javascript
import React from "react";
const Accordion = ({ title, children, index, openIndex, setOpenIndex }) => {
    return (
        <div>
            <h3 onClick={() => {
                if (openIndex === index) {
                    setOpenIndex(null);
                } else {
                    setOpenIndex(index);
                }
            }
        } >{title}{openIndex === index ? "-" : "+"}</h3>
            {openIndex === index && <div>{children}</div>}    
        </div>
    );
};

export default Accordion;
```

In the code above, we added two new props to the Accordion component: `index` and `openIndex`.

The index prop is used to identify the accordion and the `openIndex` prop is used to determine whether the accordion is open or closed. The `onClick` handler on the title of the accordion checks if the `openIndex` is equal to the index of the accordion. If it is, it sets the openIndex to null, which closes the accordion. If it is not, it sets `openIndex` to the index of the accordion, which opens the accordion.

We also need to modify our App component to manage the shared state:  
javascript

```javascript
import React, { useState } from "react";
import Accordion from "./Accordion";

const App = () => {
    const [openIndex, setOpenIndex] = useState(null);
    return (
        <div>
            <Accordion title="Section 1" index={0} openIndex={openIndex} setOpenIndex={setOpenIndex} >
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullamtincidunt velit vel nisl tempor, eget congue nisl viverra.</p>    
            </Accordion>
            <Accordion title="Section 2" index={1} openIndex={openIndex} setOpenIndex={setOpenIndex} >
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullamtincidunt velit vel nisl tempor, eget congue nisl viverra.</p>    
            </Accordion>
            <Accordion title="Section 3" index={2} openIndex={openIndex} setOpenIndex={setOpenIndex} >
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullamtincidunt velit vel nisl tempor, eget congue nisl viverra.</p>    
            </Accordion>
        </div>
    );
}

export default App;
```

### Conclusion

So, we have created a simple collapsible accordion component and then a connected collapsible accordion in React.

The singular component uses state management with the `useState` hook to determine whether the accordion is open or closed. The `onClick` handler on the title of the accordion toggles the state between open and closed.

Building a connected collapsible accordion in React is relatively simple, and it can be made even more dynamic by creating multiple accordions that only allow one to be open at a time. By using the state management provided by the `useState` hook, you can easily control the open and closed states of your accordions.

Whether you're building a FAQ section for your website or creating a dynamic user interface, the collapsible accordion is a great tool to have in your React toolkit.

Now that you have the accordion, go play with it.