# What is a Linked List?

Linked Lists are a cool data structure in computer science that is used to store and manage collections of data. It is a linear data structure that consists of a series of nodes that are linked together to form a chain. Each node in the linked list stores an item of data and a reference, known as a link, to the next node in the list.

The key advantage of linked lists over other data structures such as arrays is their dynamic size. Arrays have a fixed size and can only store a limited amount of data, whereas linked lists can grow or shrink dynamically as data is added or removed. Additionally, inserting or removing elements from an array can be time-consuming, as it requires shifting all the elements that come after the insertion or removal point. With linked lists, however, inserting or removing elements is relatively easy and efficient, as only the links between nodes need to be updated.

There are two types of linked lists: singly linked lists and doubly linked lists. Singly linked lists only store a reference to the next node in the list, while doubly linked lists store references to both the next node and the previous node.

The basic building block of a linked list is the node. A node in a linked list consists of two parts: a data item and a reference to the next node in the list.

In JavaScript, a node can be represented as a simple object with two properties: data and next.

```javascript
class Node {
  constructor(data) {
    this.data = data;
    this.next = null;
  }
}
```

To create a linked list, we simply create a series of nodes and link them together by updating the next reference of each node. For example, consider the following code that creates a linked list with three nodes:

```javascript
let node1 = new Node(1);
let node2 = new Node(2);
let node3 = new Node(3);

node1.next = node2;
node2.next = node3;
```

This creates a linked list that looks like this:

```javascript
node1 → node2 → node3
```

We can access the data in a linked list by starting at the head node and following the next references until we reach the end of the list.

In JavaScript, this can be implemented as a simple loop:

```javascript
let currentNode = node1;

while (currentNode !== null) {
  console.log(currentNode.data);
  currentNode = currentNode.next;
}
```

This loop will print the values of all the nodes in the list.

Inserting elements into a linked list is also straightforward. To insert an element into the beginning of a list, we simply create a new node with the desired data and set its next reference to the head node. To insert an element into the middle or end of a list, we iterate through the list to find the desired insertion point, and then update the next reference of the preceding node to point to the new node, and the new node's next reference to point to the original following node.

For example, to insert a node with value 4 at the beginning of the list created in the previous example, we can use the following code:

```javascript
let node4 = new Node(4);
node4.next = node1;
node1 = node4;
```

to look like this:

```javascript
node4 → node1 → node2 → node3
```

Deleting elements from a linked list is similar to inserting elements. To delete an element from the beginning of a list, we simply update the head node to point to the next node. To delete an element from the middle or end of a list, we iterate through the list to find the node preceding the node to be deleted, and then update its next reference to skip over the node to be deleted.

For example, to delete the node with value 2 from the list created in the previous example, we can use the following code:

```javascript
node1.next = node2.next;
```

This updates the linked list to look like this:

```javascript
node4 → node1 → node3
```

Linked lists can also be used to implement more advanced data structures such as stacks, queues, and trees. Stacks are a last-in, first-out (LIFO) data structure that can be implemented using a linked list, where elements are added and removed from the head of the list. Queues are a first-in, first-out (FIFO) data structure that can be implemented using a linked list, where elements are added to the end of the list and removed from the head of the list. Trees are a hierarchical data structure that can be implemented using linked lists, where each node in the list represents a node in the tree and its next reference represents a child node in the tree.

Linked lists are a versatile and efficient data structure that can be used to store and manage collections of data in a wide variety of applications. Whether you need to implement a simple list, a stack, a queue, or a tree, linked lists provide an easy and flexible solution. By understanding the basic concepts of linked lists and how to implement them in code, you can add another tool to your arsenal as a programmer and be well equipped to tackle a wide range of data management challenges.

### Uses

Linked lists are a versatile data structure that can be used in many different applications. Some interesting use cases for linked lists include:

* Dynamic memory allocation: In some systems, memory is allocated dynamically as needed, and linked lists can be used to manage this memory allocation. A linked list can be used to keep track of available memory blocks, and allocate and deallocate memory as needed.
    
* Implementing Stacks and Queues: Linked lists can be used to implement stacks and queues, which are both linear data structures that have specific insert and remove operations. Stacks follow the Last-In-First-Out (LIFO) principle, while queues follow the First-In-First-Out (FIFO) principle.
    
* Undo and Redo functionality: Many software applications have undo and redo functionality, and linked lists can be used to implement these features. In this case, a linked list can be used to keep track of the history of changes made to the document, and users can traverse the list to undo or redo changes as needed.
    
* Representing Graphs: Graphs are a type of data structure that consist of nodes and edges, and linked lists can be used to represent these relationships. In a linked list-based representation of a graph, each node in the graph is represented by a linked list node, and edges are represented by the links between these nodes.
    
* Operating System Process Scheduling: Linked lists can be used in operating systems to implement process scheduling algorithms. For example, a linked list can be used to keep track of the processes that are ready to run, and the operating system can use this linked list to decide which process to run next.
    
* Database indexing: In databases, linked lists can be used as an index structure to improve the efficiency of search operations. For example, a linked list can be used to store all the records that have a specific value in a particular field, allowing the database to quickly search for records based on this value.
    
* Web Crawling: In web crawling applications, linked lists can be used to keep track of the pages that have been visited and the pages that still need to be visited. A linked list can be used to store the URLs of the pages that have been crawled, and the URLs of the pages that still need to be crawled, allowing the web crawler to efficiently keep track of its progress.
    
* Music Playlists: Linked lists can be used to implement music playlists, where each node in the linked list represents a song. The linked list can be used to keep track of the order of the songs in the playlist, and users can add, remove, or reorder songs as needed.
    

These are just a few examples of how linked lists can be used in various applications. Their simple and flexible design makes them an attractive choice for a wide range of problems, and they are an important tool for computer scientists and software engineers to have in their toolbox.

A music playlist I made in JS using Linked Lists to showcase just how easy it is to use them:

```javascript
class Node {
    constructor(data) {
        this.data = data;
        this.next = null;
    }
}

class LinkedList {
    constructor() {
        this.head = null;
    }

    addSong(song) {
        let newNode = new Node(song);

        if (!this.head) {
            this.head = newNode;
        } else {
            let current = this.head;
            while (current.next) {
                current = current.next;
            }
            current.next = newNode;
        }
    }

    removeSong(song) {
        if (!this.head) {
            return;
        }

        if (this.head.data === song) {
            this.head = this.head.next;
            return;
        }

        let current = this.head;
        while (current.next) {
            if (current.next.data === song) {
                current.next = current.next.next;
                return;
            }
            current = current.next;
        }
    }

    displayPlaylist() {
        let current = this.head;
        while (current) {
            console.log(current.data);
            current = current.next;
        }
    }
}

let playlist = new LinkedList();

playlist.addSong("1: Dosti");
playlist.addSong("2: Naatu Naatu");
playlist.addSong("3: Komuram Bheemudo");
playlist.addSong("4: Sholay");

console.log("Playlist: ");
playlist.displayPlaylist();

playlist.removeSong("1: Dosti");

console.log("Playlist: ");
playlist.displayPlaylist();
```

Here, the `Node` class is used to represent each node in the linked list, and the `LinkedList` class is used to represent the linked list itself. The `LinkedList` class contains methods to add songs, remove songs, and display the playlist.

The `addSong` method adds a song to the end of the linked list by creating a new node with the given song and updating the next pointer of the last node in the list.

The `removeSong` method removes a song from the linked list by updating the next pointer of the previous node to skip over the node containing the song to be removed.

The `displayPlaylist` method displays the contents of the playlist by iterating through the linked list and printing the data of each node.

This is just a basic example of how linked lists can be used to implement a music playlist manager, and there are many other ways to design such a system. You can implement other Data Structures as well.

### Stacks:

A stack is a last-in, first-out (LIFO) data structure that can be implemented using a linked list, where elements are added and removed from the head of the list. In other words, the last element to be added to the stack is the first element to be removed. In a linked list implementation of a stack, we simply add new elements to the head of the list and remove elements from the head of the list.

Imagine how you would use a stack of plates. The last one to be kept is used first.

Here is how to make a stack using a linked list in JavaScript:

```javascript
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

class Stack {
  constructor() {
    this.head = null;
  }

  push(value) {
    let newNode = new Node(value);
    newNode.next = this.head;
    this.head = newNode;
  }

  pop() {
    if (!this.head) {
      return null;
    }
    let poppedNode = this.head;
    this.head = this.head.next;
    return poppedNode.value;
  }
}

let bigStack = new Stack();
bigStack.push(1);
bigStack.push(2);
bigStack.push(3);
console.log(bigStack.pop()); // outputs 3
console.log(bigStack.pop()); // outputs 2
console.log(bigStack.pop()); // outputs 1
```

### Queues:

A queue is a first-in, first-out (FIFO) data structure that can be implemented using a linked list, where elements are added to the end of the list and removed from the head of the list. In other words, the first element to be added to the queue is the first element to be removed. In a linked list implementation of a queue, we maintain two pointers, the head and the tail, to keep track of the head and end of the list. When adding an element to the queue, we simply update the tail reference to point to the new node. When removing an element from the queue, we simply update the head reference to point to the next node.

Imagine a line at the cinema for tickets, and how the one who comes earliest gets served first.

Here is how to make a queue using a linked list in JavaScript:

```javascript
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

class Queue {
  constructor() {
    this.head = null;
    this.tail = null;
  }

  enqueue(value) {
    let newNode = new Node(value);
    if (!this.head) {
      this.head = newNode;
      this.tail = newNode;
    } else {
      this.tail.next = newNode;
      this.tail = newNode;
    }
  }

  dequeue() {
    if (!this.head) {
      return null;
    }
    let dequeuedNode = this.head;
    this.head = this.head.next;
    if (!this.head) {
      this.tail = null;
    }
    return dequeuedNode.value;
  }
}

let bigQ = new Queue();
bigQ.enqueue(1);
bigQ.enqueue(2);
bigQ.enqueue(3);

console.log(bigQ.dequeue()); // outputs 1
console.log(bigQ.dequeue()); // outputs 2
console.log(bigQ.dequeue()); // outputs 3
```

### Trees:

A tree is a hierarchical data structure where each node can have multiple child nodes. A tree can be implemented using a linked list, where each node has a reference to its children. This allows us to represent a tree structure where each node has a parent node and one or more child nodes. In a linked list implementation of a tree, each node has a reference to its parent node, as well as an array of references to its child nodes.

Here's a tree using a linked list in JavaScript:

```javascript
class TreeNode {
  constructor(value) {
    this.value = value;
    this.children = [];
  }
}

class Tree {
  constructor(value) {
    this.root = new TreeNode(value);
  }

  addChild(value, parentValue) {
    let newNode = new TreeNode(value);
    let parentNode = this.findNode(this.root, parentValue);
    if (parentNode) {
      parentNode.children.push(newNode);
    }
  }

  findNode(node, value) {
    if (!node) {
      return null;
    }
    if (node.value === value) {
      return node;
    }
    for (let i = 0; i < node.children.length; i++) {
      let foundNode = this.findNode(node.children[i], value);
      if (foundNode) {
        return foundNode;
      }
    }
    return null;
  }
}

let tree = new Tree(1);

tree.addChild(2, 1);
tree.addChild(3, 1);
tree.addChild(4, 2);
tree.addChild(5, 2);
tree.addChild(6, 3);
```

Here, we have a `Tree` class that has a `root` node, which is the top-level node in the tree.

The `addChild` method is used to add a new node to the tree by finding the parent node using the `findNode` method and adding the new node to the parent's children array.

The `findNode` method uses a recursive approach to search the tree for the node with the specified value.

Here's the representation of the tree, how it would look.

```javascript
                    1
                ⬃      ⬂
             2             3
         ⬃      ⬂            ⬂
      4             5             6   
```

So Linked List may seem elusive to someone who is not familiar with Object Oriented Programming, but slow and steady learning will surely make you grasp the concept. We must also constantly keep reminding ourselves that JavaScript is not an object oriented language, so its syntax will always be more verbose than say Java or Python, which support it.

But don't forget also that you can still do it in JavaScript.