# What is up with super(props)?

#### Some Etymology for you.

The Sanskrit language has a lot of children, one such pair is "super" and "sub", coming from the words "uper"(pronounced "oopar") meaning higher, and "up"(pronounced "oop") meaning lower.

Its derivations can be seen in German, with "super" coming from "Über", which also means "high". Or in Hindi, where the Vice-president of the country is called "up-rashtrapati", where "up" is "lower". This pair of 'super' and 'sub' has trickled into computer science as well.

#### So what's up?

So here too, in React, the word `super(props)` is referring to the higher class of object in which it is written in.

The `super(props)` statement is used in the `constructor` of a class-based component to call the constructor of the component's parent class (which is React.Component) and to pass the props argument to the parent's constructor.

The `props` argument is an object that contains the properties that are passed to the component when it is rendered. By passing the `props` argument to the parent class's constructor, the component is able to access the properties passed to it, and use them to render its content.

Here's an example of a simple component that uses the `super(props)` statement in its `constructor`:

```javascript
class NamesHard extends React.Component { 
    constructor(props) { 
        super(props); 
    } 
    render() { 
        return <h1>Hello, {this.props.name}</h1>; 
    }
}
```

Here, the component is defined as a class called `NamesHard` that extends React.Component. Inside the `constructor`, `super(props)` is called to pass the props argument to the parent class's constructor.

Then, in the component's `render()` method, the component uses the [`this.props.name`](http://this.props.name) property to render a greeting message. This component can be used like this:

```javascript
<NamesHard name="Albus" />
```

This will output `"Hello, Albus"` on the page.

Interestingly if you forget to call `super(props)` in the `constructor`, it will throw an error because `this.props` will not be defined in the component class.

So basically, by calling `super(props)` in the constructor, we are allowing the component to access the props passed to it by its parent component, and also access `this.props` variable inside the component class.

That is why you have to write `super(props)` in the constructor of the Class-Based Component that you are writing, which you are not supposed to write anyway, because it is the 21st Century and you should be writing Functional Components.