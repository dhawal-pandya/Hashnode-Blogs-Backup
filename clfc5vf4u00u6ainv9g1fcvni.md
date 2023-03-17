---
title: "Sorting with Quick Sort in JavaScript"
datePublished: Fri Mar 17 2023 06:30:39 GMT+0000 (Coordinated Universal Time)
cuid: clfc5vf4u00u6ainv9g1fcvni
slug: sorting-with-quick-sort-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/FcegfS05w2c/upload/05bcf3e5175b10969d890c20bb101d0f.jpeg
tags: algorithms, javascript, coding, sorting, quick-sort

---

Quicksort is a popular and efficient sorting algorithm that uses a divide-and-conquer approach to sort an array. Quicksort is a divide-and-conquer algorithm that works by dividing an unsorted array into two sub-arrays, then recursively sorting those sub-arrays until the entire array is sorted.

To start, it chooses a "pivot" element from the array, then partitions the array into two sub-arrays: one with elements smaller than the pivot and another with elements larger than the pivot.

Then, it recursively repeats this process on each sub-array until the entire array is sorted.

In practice, quicksort is often faster than other sorting algorithms for large datasets, but its performance can be affected by the choice of the pivot and the initial ordering of the array.

### Code

Here is Quicksort in JavaScript:

```javascript
const quicksort = (array) => {
  if (array.length <= 1) {
    return array;
  }
  let pivotIndex = Math.floor(array.length / 2);
  let pivot = array[pivotIndex];
  let left = [];
  let right = [];
  for (let i = 0; i < array.length; i++) {
    if (i === pivotIndex) {
      continue;
    }
    if (array[i] < pivot) {
      left.push(array[i]);
    } else {
      right.push(array[i]);
    }
  }
  return quicksort(left).concat([pivot], quicksort(right));
}
```

In this implementation, the `quicksort` function takes an array of numbers as input and returns a sorted array.

The algorithm first checks whether the length of the input array is less than or equal to 1. If it is, the algorithm simply returns the input array, as an array of length 1 or 0 is already sorted. It is the 'if' for the recursion. This 'if' statement stops the recursion from happening indefinitely.

If the input array is longer than 1, the algorithm selects a pivot element from the array. In this implementation, the pivot element is selected as the middle element of the array, but other methods for selecting the pivot element are also possible.

The algorithm then partitions the input array into two sub-arrays: one containing elements less than the pivot element, and one containing elements greater than or equal to the pivot element. This is done using a `for` loop that iterates over the input array and adds each element to the appropriate sub-array.

The `quicksort` function then recursively calls itself on the left and right sub-arrays, and concatenates the sorted left sub-array, the pivot element, and the sorted right sub-array to produce the final sorted array.

```javascript
var myArray = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5];
var sortedArray = quicksort(myArray);
console.log(sortedArray);
// Output: [1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9]
```

Here, the `quicksort` function is called with an array of 11 numbers. The sorted array is then logged to the console, which outputs `[1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9]`.

### Use

Quicksort has an average time complexity of O(n log n), which makes it efficient for sorting large datasets. However, in the worst-case scenario where the pivot element is consistently chosen as the minimum or maximum element in the array, the time complexity can be as bad as O(n^2). To avoid this worst-case scenario, various strategies can be used to select a pivot element, such as choosing a random element or selecting the median of three elements.

Quicksort is a popular and efficient sorting algorithm that is commonly used in a wide range of applications. Some of the most common usages of Quicksort include:

1. Sorting large datasets: Quicksort is a highly efficient algorithm for sorting large datasets, with an average time complexity of O(n log n). This makes it a popular choice in applications that involve sorting large datasets, such as database management systems, scientific simulations, and financial applications.
    
2. Sorting data in-memory: Quicksort is an in-place sorting algorithm, which means that it does not require any additional memory to sort the input data. This makes it a good choice in applications where memory is a limiting factor, such as embedded systems, mobile devices, and real-time applications.
    
3. Parallel sorting: Quicksort can be easily parallelized, which means that it can be split into multiple threads or processes to speed up the sorting process. This makes it a good choice for applications that require high-performance sortings, such as scientific simulations, big data analytics, and high-performance computing.
    
4. Sorting partially ordered data: Quicksort has a good performance on partially ordered datasets, where many elements are already in the correct order. This makes it a popular choice in applications where data is frequently updated, such as search engines, social networks, and e-commerce platforms.
    
5. As a building block for other algorithms: Quicksort can be used as a building block for other algorithms, such as merge sort and heap sort. For example, the merge sort algorithm uses a divide-and-conquer approach similar to Quicksort but uses a different method to merge the sub-arrays. Quicksort can also be used as a component in other algorithms, such as sorting networks and randomized algorithms.
    

### Conclusion

Overall, Quicksort is a highly versatile sorting algorithm that is widely used in a range of applications, from database management systems and scientific simulations to search engines and e-commerce platforms. Its high performance, low memory overhead, and parallelizability make it an attractive choice for applications that require efficient and scalable sorting.

It is really fast, but you must know it before you apply it. Read the process again if it is not clear enough in the first read.