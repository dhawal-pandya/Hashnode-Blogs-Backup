---
title: "Solving Merge Two Sorted Lists"
datePublished: Sat Apr 15 2023 06:30:39 GMT+0000 (Coordinated Universal Time)
cuid: clghln4vd02too9nv1mk242wv
slug: solving-merge-two-sorted-lists
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/RLw-UC03Gwc/upload/f66c930c12065551ccd793d883baa24e.jpeg
tags: algorithms, data-structures, solution, dsa, merge-two-sorted-linked-lists

---

Merge Two Sorted Lists is a classic problem in computer science that requires the merging of two sorted linked lists into a single sorted linked list. This problem is often used in coding interviews for software engineering positions and is a good test of a programmer's ability to manipulate linked lists and write efficient algorithms. It is an important concept in computer science and is commonly encountered in real-world software engineering. Linked lists are fundamental data structures used to represent sequences of elements in computer programs.

They are useful when the size of the list is unknown at compile-time or when elements need to be inserted or removed efficiently.

### The Premise

The problem of merging two sorted linked lists is a common coding question that asks the programmer to combine two sorted linked lists into a single sorted linked list. The premise of the problem is that we are given two linked lists, list1, and list2, which are already sorted in ascending order, and we are asked to merge them into a newly sorted linked list.

The resulting merged list should also be sorted in ascending order, and the elements from both input lists should be present in the merged list. The problem statement often provides the definition of the ListNode class, which represents a single node in the linked list, and contains a `val` attribute for the value of the node, and a `next` attribute for the reference to the next node in the list.

### Noob Solution

A simple algorithm for solving this problem is to create a new linked list, and then loop through both input lists, comparing the heads of each list and appending the smaller node to the new list. Once we have reached the end of one of the input lists, we simply append the remaining nodes from the other list to the end of the new list.

Here's the first intuitive code:

In JS:

```javascript
class ListNode {
  constructor(val = 0, next = null) {
    this.val = val;
    this.next = next;
  }
}

const mergeTwoLists = (l1, l2) => {
  const dummy = new ListNode(0);
  let curr = dummy;

  while (l1 && l2) {
    if (l1.val < l2.val) {
      curr.next = l1;
      l1 = l1.next;
    } else {
      curr.next = l2;
      l2 = l2.next;
    }
    curr = curr.next;
  }

  if (l1) {
    curr.next = l1;
  } else if (l2) {
    curr.next = l2;
  }

  return dummy.next;
}
```

In Python:

```javascript
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

def mergeTwoLists(l1, l2):
    dummy = ListNode(0)
    curr = dummy
    while l1 and l2:
        if l1.val < l2.val:
            curr.next = l1
            l1 = l1.next
        else:
            curr.next = l2
            l2 = l2.next
        curr = curr.next
    if l1:
        curr.next = l1
    elif l2:
        curr.next = l2
    return dummy.next
```

In this implementation, we create a dummy node to serve as the head of our new list, and a current node to keep track of where we are in the new list. We then loop through the two input lists, comparing the heads and appending the smaller node to the new list. Once we have exhausted one of the input lists, we simply append the remaining nodes from the other list to the end of the new list.

This algorithm has a time complexity of O(m + n), where m and n are the lengths of the input lists. However, there are ways to optimize this algorithm to reduce its time complexity.

### Pro Solution

One way to optimize the algorithm is to use recursion instead of a while loop. In this approach, we compare the heads of the two input lists and recursively call the function with the remaining sublists until one of the lists is empty. We then append the remaining nodes from the non-empty list to the end of the merged list.

In JS:

```javascript
class ListNode {
  constructor(val = 0, next = null) {
    this.val = val;
    this.next = next;
  }
}

const mergeTwoLists = (l1, l2) => {
    if (!l1) return l2;
    if (!l2) return l1;
    if (l1.val < l2.val) {
        l1.next = mergeTwoLists(l1.next, l2);
        return l1;
    } else {
        l2.next = mergeTwoLists(l1, l2.next);
        return l2;
    }
}
```

In Python:

```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

def mergeTwoLists(l1, l2):
    if not l1:
        return l2
    if not l2:
        return l1
    if l1.val < l2.val:
        l1.next = mergeTwoLists(l1.next, l2)
        return l1
    else:
        l2.next = mergeTwoLists(l1, l2.next)
        return l2
```

In this implementation, we first check if either of the input lists is empty. If one of the lists is empty, we simply return the other list. If neither list is empty, we compare the heads of the two lists and recursively call the function with the remaining sublists until one of the lists is empty. We then append the remaining nodes from the non-empty list to the end of the merged list.

This recursive approach has a time complexity of O(m + n) and can be more efficient than the iterative approach for certain input sizes.

### Conclusion

The problem of merging two sorted linked lists is particularly useful when dealing with sorted data sets, which are common in many applications. For example, consider an e-commerce platform that needs to merge two sorted lists of products, one sorted by price and the other sorted by popularity, to create a new list that is sorted by both price and popularity. In this scenario, the merging of two sorted lists is a critical operation that can impact the performance of the platform.

Additionally, many algorithms in computer science rely on merging sorted lists as a subroutine. For example, the merge sort algorithm, which is widely used in sorting algorithms, employs a recursive algorithm to merge two sorted lists in order to produce a sorted output.

Overall, the problem of merging two sorted linked lists is a fundamental algorithmic problem that has a wide range of real-world applications and is an important building block in many algorithms.