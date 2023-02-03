# DOM vs BOM. What gives?

BOM (Browser Object Model) and DOM (Document Object Model) are both web technologies used to represent and manipulate the structure and content of a web page. However, they serve different purposes and are used in different ways.

The BOM represents the browser window and provides a set of objects that allow us to interact with and control the browser window and its properties. For example, the BOM provides objects for manipulating the browser window size, managing cookies, and opening new windows.

The DOM, on the other hand, represents the content and structure of a web page and provides a set of objects and methods for accessing and manipulating the elements of a web page, such as HTML tags, text, images, and links. The DOM also provides a way to listen for events, such as a user clicking on a button or scrolling the page, and respond to these events with custom code.

To use the BOM, we can access the window object in JavaScript, which is the top-level object in the BOM, and use its properties and methods to interact with the browser window. For example, we can use the [window.open](http://window.open)() method to open a new browser window, or the window.innerWidth property to get the width of the window.

To use the DOM, we can access the document object in JavaScript, which represents the HTML document and provides a set of methods for accessing and manipulating the elements of the page. For example, we can use the document.getElementById() method to access a specific element on the page based on its id, or the document.createElement() method to create a new element and add it to the page.

Here are some examples of BOM and DOM:

BOM Example:

* Opening a new window:
    

```javascript
const newWindow = window.open("https://www.example.com", "Example", "width=500, height=500");
```

* Getting the screen width and height:
    

```javascript
const screenWidth = window.screen.width; 
const screenHeight = window.screen.height;
```

* Setting a cookie:
    

```javascript
document.cookie = "username=Albus; expires=Sun, 9 Oct 2997 12:00:00 UTC; path=/";
```

DOM Example:

* Accessing an element by its id:
    

```javascript
const header = document.getElementById("header");
```

* Changing the text of an element:
    

```javascript
document.getElementById("header").innerHTML = "Namaste";
```

* Adding a new element to the page:
    

```javascript
const newElement = document.createElement("p"); 
newElement.innerHTML = "This is a new paragraph, you dumdum!"; document.body.appendChild(newElement);
```

* Listening for a click event:
    

```javascript
document.getElementById("button").addEventListener("click", () => {  
    alert("Button clicked and NASA hacked using HTML"); 
});
```

These are just a few examples of how BOM and DOM can be used to manipulate the browser window and the content of a web page. There are many more objects and methods available in both BOM and DOM that allow you to create rich and dynamic web applications.

So basically, the BOM provides a way to interact with and control the browser window, while the DOM provides a way to access and manipulate the content and structure of a web page. Both technologies are essential for creating dynamic and interactive web applications.

So stop watching 'those' movies and get to work.