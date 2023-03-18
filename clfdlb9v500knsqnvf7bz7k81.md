---
title: "Sorting with Merge Sort in JavaScript"
datePublished: Sat Mar 18 2023 06:30:39 GMT+0000 (Coordinated Universal Time)
cuid: clfdlb9v500knsqnvf7bz7k81
slug: sorting-with-merge-sort-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/nShLC-WruxQ/upload/4ae2d705d766e15a188acba64ece7bb3.jpeg
tags: algorithms, javascript, coding, sorting, merge-sort

---

Merge sort is a popular sorting algorithm that uses the divide-and-conquer approach to sort an array or a list of elements. In merge sort, the input array is divided into two halves, sorted recursively, and then merged back together in sorted order. The merging process is the key component of merge sort, and it involves comparing the elements of the two sub-arrays and placing them in the correct order in a new array.

The algorithm starts by dividing the input array into two halves and recursively sorting each half. This is done until the base case is reached, which occurs when the sub-arrays have only one element. Once the base case is reached, the algorithm merges the sorted sub-arrays. This is done by comparing the first elements of each sub-array and adding the smallest element to a new array. This process continues until all elements have been added to the new array, resulting in a fully sorted array.

The key to merge sort's efficiency is the merging step, which has a time complexity of O(n) and works by efficiently combining two sorted sub-arrays into a single sorted array. Because merge sort recursively divides the input array into halves, its time complexity is O(n\*log(n)), which is faster than the O(n^2) time complexity of algorithms like bubble sort and insertion sort for large datasets.

### Pseudo-code

Here is the process of Merge sort:

1. Divide the unsorted list into n sub-lists, each containing one element (a list of one element is considered sorted).
    
2. Repeatedly merge sub-lists to produce new sorted sub-lists until there is only one sub-list remaining. This will be the sorted list.
    

### Code

Here is the code of Merge sort in JavaScript:

```javascript
const merge = (leftArray, rightArray) => {
  const resultArray = [];

  let leftIndex = 0;
  let rightIndex = 0;

  // Compare the elements of the two sub-arrays and place them in the correct order
  while (leftIndex < leftArray.length && rightIndex < rightArray.length) {
    if (leftArray[leftIndex] < rightArray[rightIndex]) {
      resultArray.push(leftArray[leftIndex]);
      leftIndex++;
    } else {
      resultArray.push(rightArray[rightIndex]);
      rightIndex++;
    }
  }

  // Add any remaining elements from the left or right sub-arrays
  return resultArray
    .concat(leftArray.slice(leftIndex))
    .concat(rightArray.slice(rightIndex));
}

const mergeSort = (arr) => {
  // Base case
  if (arr.length <= 1) {
    return arr;
  }

  // Divide the array into two halves
  const middleIndex = Math.floor(arr.length / 2);
  const leftArray = arr.slice(0, middleIndex);
  const rightArray = arr.slice(middleIndex);

  // Recursively sort the left and right halves
  const sortedLeftArray = mergeSort(leftArray);
  const sortedRightArray = mergeSort(rightArray);

  // Merge the sorted halves back together
  return merge(sortedLeftArray, sortedRightArray);
};
```

In this implementation, the `mergeSort()` function recursively divides the input array into two halves and sorts them using the `merge()` function. The `merge()` function compares the elements of the two sub-arrays and places them in the correct order in a new array, which is returned as the result.

```javascript
var myArray = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5];
var sortedArray = mergeSort(myArray);
console.log(sortedArray);
// Output: [1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9]
```

### Use

Overall, Merge sort is a highly efficient sorting algorithm with a time complexity of O(n log n). It is commonly used in a wide range of applications, such as database management systems, scientific simulations, and financial applications, where efficient and scalable sorting is required.

Merge sort is a highly efficient sorting algorithm and is commonly used in a wide range of applications where efficient and scalable sorting is required. Some of the common usages of Merge sort are:

1. Sorting large datasets: Merge sort is highly efficient and has a time complexity of O(n log n). It is ideal for sorting large datasets, where other sorting algorithms may become inefficient.
    
2. External sorting: Merge sort is commonly used in external sorting, where data is too large to fit into the memory. Merge sort can handle such cases by dividing the data into smaller chunks that can be sorted and then merged back together.
    
3. Parallel processing: Merge sort can be easily parallelized, which makes it suitable for distributed systems and multi-core processors.
    
4. Database management systems: Merge sort is widely used in database management systems to sort large amounts of data. It is often used for sorting indexes, which helps to improve query performance.
    
5. Scientific simulations: Merge sort is used in various scientific simulations that involve sorting large datasets, such as weather forecasting and molecular dynamics simulations.
    

### Conclusion

When it comes to sorting, there is no one-size-fits-all solution, and choosing the right algorithm depends on several factors, including the size and structure of the dataset, available memory, and desired performance characteristics.

Nonetheless, Merge Sort is an essential algorithm that every computer scientist should be familiar with, and it provides a solid foundation for understanding more complex algorithms such as quicksort, heapsort, and others.

#peace.