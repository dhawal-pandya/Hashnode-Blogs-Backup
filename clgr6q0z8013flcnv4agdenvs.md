---
title: "Solving Invert Binary Tree"
datePublished: Fri Apr 21 2023 23:30:42 GMT+0000 (Coordinated Universal Time)
cuid: clgr6q0z8013flcnv4agdenvs
slug: solving-invert-binary-tree
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/3iRWO-CQx2w/upload/02bcd91af0b615bc490525369b32c81c.jpeg
tags: algorithms, data-structures, solution, dsa, invert-binary-tree

---

Binary trees are an important data structure used in computer science and programming. They are a type of tree data structure where each node has at most two children, known as the left child and right child. The root of the tree is the topmost node, while the leaf nodes are the nodes with no children.

Binary trees are commonly used in algorithms for searching and sorting data, as well as in the implementation of other data structures such as heaps and binary search trees. Understanding binary trees is essential for any programmer seeking to master data structures and algorithms.

## The Premise

The problem asks us to invert a binary tree, i.e., swap the left and right subtrees of each node in the given binary tree, and return the root of the modified tree.

```markdown
     4
   /   \
  2     7
 / \   / \
1   3 6   9
```

...must become...

```markdown
     4
   /   \
  7     2
 / \   / \
9   6 3   1
```

## Noob Solution

A simple approach to solving the problem is to traverse the binary tree recursively and swap the left and right subtrees of each node. We can implement this using a depth-first search (DFS) algorithm.

Here's the code for the same:

In JS:

```javascript
const invertTree = (root) => {
  if (!root) {
    return null;
  }
  
  const temp = root.left;
  root.left = invertTree(root.right);
  root.right = invertTree(temp);
 
  return root;
}
```

In Python:

```python
def invertTree(root):
    if not root:
        return None

    temp = root.left
    root.left = invertTree(root.right)
    root.right = invertTree(temp)

    return root
```

In the above code, we first check if the root of the tree is `null`. If yes, then we return `null`.

Otherwise, we swap the left and right subtrees of the current node using a temporary variable `temp` and recursively call the `invertTree` function on the left and right subtrees of the current node. Finally, we return the root of the modified tree.

## Pro Solution

The noob solution has a time complexity of O(n), where n is the number of nodes in the binary tree, as we need to visit each node once. However, we can optimize the solution further using an iterative approach instead of a recursive one, as recursion can lead to stack overflow errors for very large trees.

We can implement the same DFS algorithm using a stack data structure to keep track of the nodes to be processed.

Here's the optimized code:

In JS:

```javascript
const invertTree = (root) => {
  if (!root) {
    return null;
  }
  
  const stack = [root];
  
  while (stack.length > 0) {
    const node = stack.pop();
    const temp = node.left;
    node.left = node.right;
    node.right = temp;
    
    if (node.left) {
      stack.push(node.left);
    }
    
    if (node.right) {
      stack.push(node.right);
    }
  }
  
  return root;
}
```

In Python:

```python
def invertTree(root):
    if not root:
        return None
    
    stack = [root]
    
    while stack:
        node = stack.pop()
        temp = node.left
        node.left = node.right
        node.right = temp
        
        if node.left:
            stack.append(node.left)
        
        if node.right:
            stack.append(node.right)
    
    return root
```

In the above code, we first check if the root of the tree is `null`. If yes, then we return `null`.

Otherwise, we create a stack data structure and push the root of the tree onto it. We then enter a loop that runs until the stack is empty.

Inside the loop, we pop a node from the stack, swap its left and right subtrees using a temporary variable `temp` and push its left and right subtrees onto the stack (if they exist).

Finally, we return the root of the modified tree.

## Conclusion

Inverting a binary tree is an important question because it has real-world applications in computer science, particularly in data structures and algorithms. Inverting a binary tree can be used to optimize searching and sorting algorithms, and it can also be useful in computer graphics, as it can help to render images more efficiently.

Furthermore, inverting a binary tree is a good exercise in understanding and manipulating binary trees, which are fundamental data structures in computer science. It helps to build problem-solving skills and logical thinking, which are important skills for any computer scientist or software engineer.

This one is only slightly less important than reversing a linked-list.