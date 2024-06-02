---
title: "Why (not) semicolons in JavaScript?"
datePublished: Sat Feb 18 2023 11:30:39 GMT+0000 (Coordinated Universal Time)
cuid: cle9vp89c03c5conv225x9x3x
slug: why-not-semicolons-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/cvBBO4PzWPg/upload/3528784117353941ce7325be60a1ad19.jpeg
tags: c, javascript, english, semicolons, semicolon

---

Semicolons have a long history in programming, and their importance in JavaScript is no exception. Let's explore the history of semicolons in programming, the role they play in JavaScript, and why they are considered an important part of the language.

### History of Semicolons (ignorable)

The semicolon has a long history dating back to the 15th century. It is believed to have been first used by Italian printer and publisher Aldus Manutius in 1494. The semicolon was created as a way to separate words and phrases within a sentence, and it was initially used primarily in Greek texts.

In English, the semicolon was first introduced by the English writer and printer William Caxton in the late 15th century. Over time, the semicolon became increasingly popular among writers and was used to separate independent clauses that were closely related in meaning but not joined by a coordinating conjunction.

The use of the semicolon reached its peak in the 18th and 19th centuries when it was widely used by writers such as Samuel Johnson, Jane Austen, and Charles Dickens. Today, the semicolon remains an important punctuation mark in English, though its usage has become somewhat less common in modern writing.

### Use in English (ignorable)

In English, semicolons (;) are used to join two closely related independent clauses (complete sentences) that could stand alone as separate sentences but are closely connected in meaning. Semicolons are often used instead of a coordinating conjunction (such as "and," "but," or "or") to emphasize the relationship between the two clauses.

Semicolons can also be used to separate items in a list when the items themselves contain commas, to avoid confusion. Additionally, they can be used to separate independent clauses joined by conjunctive adverbs (such as "however," "therefore," or "nevertheless").

```plaintext
The size of my shoes is bigger than average; I don't expect anyone 
to draw any weird conclusions from that.
```

### Use in Programming (the main point)

Semicolons have a long history in programming, and their importance in JavaScript is no exception.

The origin of semicolons in programming dates back to the early days of computing. In the early 1960s, the first high-level programming languages were created, including COBOL and FORTRAN. These languages used semicolons to separate statements, making it easier for programmers to write and read code. It is because there is no real answer to, 'what can we truly use, which is already on the keyboard, and does not have multiple functions associated with it?'

### Use in JavaScript

In JavaScript, they are used to separate statements and indicate the end of a line of code.

```javascript
let x = 10; let y = 20; let z = x + y;
```

Without semicolons, the code would be harder to read and maintain.

In some cases, automatic semicolon insertion can lead to unexpected results. For example:

```javascript
let x = 10 let y = 20 let z = x + y
```

In this code, automatic semicolon insertion will insert semicolons in the expected places, but the code will still work as expected. However, this can lead to confusion and make the code harder to understand and maintain.

It's important to note that JavaScript does not require semicolons in all cases. The language uses automatic semicolon insertion, which automatically inserts semicolons in certain situations. However, it is considered best practice to include semicolons in your code to avoid potential errors and make your code easier to read and maintain.

There are some situations where semicolons are required in JavaScript. For example, when writing a `for` loop, you must include a semicolon after the `for` keyword to separate the `for` a statement from the loop body:

```javascript
for (let i = 0; i < 10; i++) { console.log(i); }
```

In this code, the semicolon after the for keyword separates the `for` statement from the loop body, making the code easier to read and maintain.

### Automatic Semicolon Insertion

The JavaScript parser will automatically add a semicolon when, during the parsing of the source code, it finds these particular situations:

* when the next line starts with code that breaks the current one (code can spawn on multiple lines)
    
* when the next line starts with a `}`, closing the current block
    
* when the end of the source code file is reached
    
* when there is a `return` statement on its own line
    
* when there is a `break` statement on its own line
    
* when there is a `throw` statement on its own line
    
* when there is a `continue` statement on its own line
    

### Conclusion

Semicolons are an important part of JavaScript, and their origin dates back to the early days of programming. They serve to separate statements and indicate the end of a line of code, making the code easier to read and maintain. Although automatic semicolon insertion is built into the language, it is considered best practice to include semicolons in your code to avoid potential errors and make your code easier to understand and maintain. Whether you are a beginner or an experienced JavaScript programmer, understanding the role of semicolons in the language is critical for writing effective and efficient code.