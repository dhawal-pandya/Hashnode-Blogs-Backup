# Let me 'Hoist' this up

Let’s take the detour…

If you check the typeof(null), it will always return an ‘object’. This is a bug, as admitted by Brendan himself. Due to legacy reasons, it will never be fixed, and we have to live with that. 

Similarly, the other thing we have to accept as a cute quirk of JavaScript is the difference between ‘undefined’ and ‘not defined’. 

```javascript
var a = 'Albus';
var b = null;
var c;

console.log(a); // Albus
console.log(b); // null
console.log(c); // undefined
console.log(d); // Reference Error ...not defined...
```

a is declared and defined as a string, “Albus”.

b is declared and defined with null.

c is declared, but it is not defined.

d is neither declared nor defined.

“Undefined” is a placeholder, for variables that are declared but not defined yet. So wherever JS finds a variable that is declared using ‘var’, but it is not given any value (also known as being defined), it puts ‘undefined’ as its placeholder. 

JavaScript Engine has a very peculiar interpreter. It reads the whole code and marks out all variables and functions in its storage. For the functions, i.e: when the code encounters a function declared using the ‘function’ keyword, it will store its name, as well as all its contents, without trying to make sense of its contents. Just the whole block of code written in a function is stored directly, word for word.

For the variables, it just stores their names, without memorizing their values. The actual values are added to the code when it reads the code and starts executing it line by line.

For example:

```javascript
var a = "Albus";
```

This is just stored in the storage as if the code has a variable ‘a’ without any value (like the string here).

But the JavaScript Engine has a special placeholder for variables that haven’t been defined yet, and that is “undefined”.

Hence, for all intents and purposes, 

```javascript
a = undefined;
```

This is what happened with ‘c’ in our earlier code block.

But when the code starts executing line by line, at that time, the value of ‘a’ is populated with “Albus”.

Like so:

```javascript
console.log(a); // undefined
var a = "Albus";
console.log(a); // "Albus"
console.log(b); // Reference Error ...not defined...
```

Observe that the code didn’t say ‘not defined’ for ‘a’, but only for ‘b’.

What we learn from this is that the code is technically read twice. In the first reading, only the variables and functions are collected, and stored in their unique ways, and while executing we actually see them manifest.

My code tried to access ‘a’ before it was declared, and still, my Engine acknowledged the existence of ‘a’, just not its value, unlike with ‘b’ for whom it said that it simply did not exist.

The “First Reading” is technically called the “Memory Creation Phase”, and the “Second Reading” is technically called the “Execution Phase”.

So observe that when the JavaScript Engine is in the second phase, it already has all the functions memorized. Even if a function is declared at the end of the code, it is still the memory of the Engine. Hence we can call a function before it is declared.

```javascript
calledHere(); // "This will be logged"

// ...lines of code...

function calledHere() {
  console.log('This will be logged');
}
```

All functions that are declared using the ‘function’ keyword, will behave like this. That is because in the Execution Phase when the code encounters the call of the function, it already has the content of that function in its memory, so it can execute it without errors. 

This behavior of the code to act as if the declarations of the functions existed before they were called, or in other words, as if all the function declarations exist at the top of the code. is called “Hoisting”. 

Just like a flag is hoisted to the top, all the functions are available for calling anywhere in the code without errors. Keep in mind that the Engine doesn’t actually move the code to the top of the file, just that it behaves as if it did.

This quirk must imbue you with a lot of questions like, 

Does hoisting occur within scopes? Are classes hoisted? What are the errors of ‘initialization’? Let’s try to answer them one by one.

Hoisting in Scopes?

```javascript
bcal();

var b = 1;

function bcal() {
  console.log(b);
  var b = 2;
}
```

We know that the function ‘bcal’ will be executed. But what shall the value of ‘b’ be logged as? 

Very interestingly, it will output ‘undefined’, even though I declared ‘b’ twice. 

All blocks of code have their own two phases. If I had not declared ‘b’ as 2, it would have looked for ‘b’ in the contents of the function and on not finding it, it would have gone to the global context to look for it. There it would find the value of ‘b’ as 1 and log that in the console. But in the Memory Creation Phase for the block of ‘bcal’ it remembered that there is a variable called ‘b’, just not what its value is. Hence, it gave ‘undefined’.

I invite you to play around with that code to figure out and confirm what I am saying. Merging scope and hoisting is really fun and gives a great insight into how to debug your code more efficiently.

What about classes? What’s ‘Initialization’?

```javascript
var thing = new Thing(1, 0);

class Thing{
  constructor(x, y) {
    this.x = x;
    this.y = y;
  }
}

console.log(thing);
// hoisted technically, but not initialized
```

Here, a very unique type of error is displayed. The JavaScript Engine will tell you that the Class exists, but you’ve declared it after instancing it. Meaning, that the Engine knows that the class exists, just not what it contains. So the instance I declared using var, is not just ‘undefined’ as a placeholder, but actually throws an error. Pretty cool, right?

So the classes are hoisted technically, i.e: the existence of such a class is known by the Engine, but not what it contains. So we say that the class is not initialized.

Hoisting occurs with classes, but it is quite useless, and hence we must write it properly, meaning initialize it before instancing it. Like so:

```javascript

class Thing {
  constructor(x, y) {
    this.x = x;
    this.y = y;
  }
}

var thing = new Thing(1, 2);

console.log(thing);
```

And this will work perfectly.

This behavior is not seen in compiled languages like Python, C++, Java, etc.

The way the community of JavaScript has combated this quirk of ‘hoisting’ is by introducing “let” and “const” for declaring variables and ‘arrow functions’ for declaring functions. If you write your code using them instead of “var” and “function”, you will not have to worry about hoisting. 

But if you want to debug code written by other people, or simply work in an environment where the legacy constraints are to be observed, then it pays well to understand hoisting perfectly. 

JavaScript has also evolved with the people who use the language, and these quirks make it feel like a living, breathing organism evolving into a better product.