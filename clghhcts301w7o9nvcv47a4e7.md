---
title: "Solving Valid Parentheses I"
datePublished: Sat Apr 15 2023 04:30:40 GMT+0000 (Coordinated Universal Time)
cuid: clghhcts301w7o9nvcv47a4e7
slug: solving-valid-parentheses-i
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/NL_DF0Klepc/upload/526bbf3c0df977225270dc969a021a80.jpeg
tags: algorithms, data-structures, solution, dsa, valid-parentheses-i

---

Valid Parentheses I is a classic coding problem that requires checking whether a given string of parentheses is valid or not.

Valid Parentheses is an important question because it tests a fundamental skill in programming: the ability to implement data structures and algorithms to solve problems. It requires the use of a stack data structure and a simple algorithm to check if a string of parentheses is valid or not.

### The Premise

Given a string containing just the characters '(', ')', '{', '}', '\[' and '\]', determine if the input string is valid. An input string is valid if:

1. Open brackets must be closed by the same type of brackets.
    
2. Open brackets must be closed in the correct order.
    

### Noob Solution

One intuitive solution to this problem is to use a stack data structure to keep track of the opening brackets. We can iterate through the string, and if we encounter an opening bracket, we push it onto the stack. If we encounter a closing bracket, we pop the top element from the stack and check if it matches the corresponding opening bracket. If it does not match, the string is not valid. If we reach the end of the string and the stack is empty, the string is valid.

Here is the less optimized code:

In JS:

```javascript
const isValid = (s) => {
  const stack = [];

  for (let i = 0; i < s.length; i++) {
    if (s[i] === '(' || s[i] === '{' || s[i] === '[') {
      stack.push(s[i]);
    } else {
      const top = stack.pop();
      if ((s[i] === ')' && top !== '(') || (s[i] === '}' && top !== '{') || (s[i] === ']' && top !== '[')) {
        return false;
      }
    }
  }

  return stack.length === 0;
}
```

In Python:

```javascript
def isValid(s):
    stack = []

    for char in s:
        if char == '(' or char == '{' or char == '[':
            stack.append(char)
        else:
            if not stack:
                return False
            top = stack.pop()
            if (char == ')' and top != '(') or (char == '}' and top != '{') or (char == ']' and top != '['):
                return False

    return len(stack) == 0
```

The main difference is that in Python, we use `len(stack)` instead of `stack.length` to get the size of the stack. We also use `char` instead of `s[i]` to get the current character in the string.

### Pro Solution

The less optimized solution has a time complexity of O(n), where n is the length of the string. This is because we need to iterate through the entire string once to check if it is valid.

We can optimize this solution by using a hash map to store the corresponding closing brackets for each opening bracket. This way, we can avoid using multiple if statements to check if the closing bracket matches the opening bracket. We can also use a Set to store the opening brackets to make the code more concise.

Here is the more optimized code:

In JS:

```javascript
const isValid = (s) => {
  const stack = [];
  const map = {
    '(': ')',
    '{': '}',
    '[': ']'
  };
  const openings = new Set(['(', '{', '[']);

  for (let i = 0; i < s.length; i++) {
    if (openings.has(s[i])) {
      stack.push(s[i]);
    } else {
      const top = stack.pop();
      if (map[top] !== s[i]) {
        return false;
      }
    }
  }

  return stack.length === 0;
}
```

In Python:

```javascript
def isValid(s: str) -> bool:
    stack = []
    mapping = {
        '(': ')',
        '{': '}',
        '[': ']'
    }
    openings = set(['(', '{', '['])

    for char in s:
        if char in openings:
            stack.append(char)
        else:
            if not stack or mapping[stack.pop()] != char:
                return False

    return not stack
```

The optimized solution has the same time complexity of O(n), but it is more concise and efficient.

### Conclusion

This question is often asked in technical interviews for software engineering positions because it tests multiple skills at once, including problem-solving, algorithm design, and coding proficiency. It also requires a solid understanding of data structures and how to implement them in code.

In addition, Valid Parentheses I is a common problem that appears in coding competitions and coding challenges. Being able to solve this problem quickly and efficiently can improve a programmer's coding skills and problem-solving abilities.