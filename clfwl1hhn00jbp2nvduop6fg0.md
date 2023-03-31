---
title: "Searching with Binary Search in JavaScript"
datePublished: Fri Mar 31 2023 13:30:39 GMT+0000 (Coordinated Universal Time)
cuid: clfwl1hhn00jbp2nvduop6fg0
slug: searching-with-binary-search-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/6AL5ong0mFQ/upload/76a21b6dc9e5483286fa5ff010e841cd.jpeg
tags: algorithms, javascript, coding, binary-search-algorithm, searching-algorithms

---

Binary Search is a search algorithm that works by repeatedly dividing the search interval in half. It is a very efficient algorithm for searching sorted arrays or lists.

Binary Search has a time complexity of O(log n), which means that the time it takes to search through the array or list increases logarithmically with the size of the input data. This makes it much faster than linear search, which has a time complexity of O(n). The time complexity of the binary search is O(log n)as the size of the search interval is reduced by half in every iteration.

Binary Search has several advantages over other searching algorithms. It is very efficient for large datasets, and it is also very easy to implement. Additionally, it can be used to search for elements in any sorted data structure, including arrays, linked lists, and trees.

### Logic

* The algorithm begins by comparing the target value with the middle element of the sorted array or list.
    
* If the target value is equal to the middle element, then the search is successful, and the index of the middle element is returned.
    
* If the target value is less than the middle element, then the search continues on the lower half of the array or list.
    
* If the target value is greater than the middle element, then the search continues on the upper half of the array or list.
    
* This process is repeated until the target value is found or the search interval is empty.
    

### Code

Here is the Binary Search algorithm in JavaScript:

```javascript
const binarySearch = (array, target) => { 
    let left = 0; 
    let right = array.length - 1;
    while (left <= right) { 
        const middle = Math.floor((left + right) / 2); 
        if (array[middle] === target) { 
            return middle; 
        } else if (array[middle] < target) { 
            left = middle + 1; 
        } else { 
            right = middle - 1; 
        } 
    }
    return -1; 
}
```

In this implementation, the binarySearch function takes an array and a target value as input parameters. It initializes two pointers, left and right, to the first and last indices of the array, respectively.

The function then enters a while loop that runs until the left pointer is greater than the right pointer, indicating that the search interval is empty. In each iteration of the loop, the function calculates the index of the middle element of the search interval using the formula (left + right) / 2. It then compares the target value to the middle element of the array.

If the target value is equal to the middle element, the function returns the index of the middle element. If the target value is less than the middle element, the function updates the right pointer to the index immediately to the left of the middle element. If the target value is greater than the middle element, the function updates the left pointer to the index immediately to the right of the middle element.

If the target value is not found in the array, the function returns -1.

```javascript
const array = [1, 1, 2, 3, 5, 8, 13, 19]; 
const target = 5; 
const result = binarySearch(array, target);
console.log(result); // Output: 4
```

### Uses

Binary Search is a very useful algorithm and can be applied in various situations. Here are some common uses of Binary Search:

1. Searching in large datasets: Binary Search is especially useful for searching in large datasets. Since it has a time complexity of O(log n), it is much faster than linear search, which has a time complexity of O(n). Therefore, Binary Search is commonly used in applications that involve searching large databases or collections of records.
    
2. Finding the position of an element in a sorted array: Binary Search is very efficient at finding the position of an element in a sorted array. This is because it repeatedly divides the search interval in half, quickly narrowing down the search to a single element. Therefore, Binary Search is commonly used in applications that involve searching for a specific element in a sorted array, such as searching for a word in a dictionary.
    
3. Implementing data structures: Binary Search can be used to implement various data structures, such as binary trees, heaps, and priority queues. For example, Binary Search can be used to find the minimum or maximum element in a binary tree or to maintain a sorted order of elements in a priority queue.
    
4. Sorting algorithms: Binary Search is used in various sorting algorithms, such as quicksort and mergesort, to divide the input data into smaller subproblems. For example, quicksort uses Binary Search to partition the input array into two subarrays, one containing elements smaller than the pivot element and one containing elements greater than the pivot element.
    

### Conclusion

However, Binary Search does have some limitations. It requires the data to be sorted, which can be a time-consuming process, especially for large datasets. Additionally, it cannot be used for searching unsorted data or for finding multiple occurrences of the same value in a dataset.

Despite these limitations, Binary Search remains one of the most widely used search algorithms due to its efficiency and ease of implementation.