---
title: "Sorting with Heap Sort in JavaScript"
datePublished: Sun Mar 19 2023 06:30:39 GMT+0000 (Coordinated Universal Time)
cuid: clff0r4da00khesnv0jzv1598
slug: sorting-with-heap-sort-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/mm4r_icYJc4/upload/44888ce4661d02364c59e291536ee62a.jpeg
tags: algorithms, javascript, coding, sorting, heap-sort

---

Heap sort is a sorting algorithm that uses a binary heap data structure to sort an array or a list of elements. In heap sort, the input array is first converted into a binary heap, and then the maximum element is repeatedly removed from the heap and added to the sorted array. The process of removing the maximum element from the heap and adding it to the sorted array is repeated until the heap is empty, resulting in a sorted array.

### Pseudo-code

Here is the process of Heap sort:

1. Build a max heap from the input array.
    
2. Replace the root node with the last element of the heap and reduce the heap size by 1.
    
3. Heapify the new root node to maintain the max heap property.
    
4. Repeat steps 2-3 until the heap is empty.
    
5. The sorted array is the reverse of the order in which the elements were removed from the heap.
    

### Code

Here is the code of Heap sort: in JavaScript:

```javascript
const swap = (arr, i, j) => {
  const temp = arr[i];
  arr[i] = arr[j];
  arr[j] = temp;
}

const heapify = (arr, index, heapSize) => {
  const leftIndex = 2 * index + 1;
  const rightIndex = 2 * index + 2;
  let largestIndex = index;

  if (leftIndex < heapSize && arr[leftIndex] > arr[largestIndex]) {
    largestIndex = leftIndex;
  }

  if (rightIndex < heapSize && arr[rightIndex] > arr[largestIndex]) {
    largestIndex = rightIndex;
  }

  if (largestIndex !== index) {
    swap(arr, index, largestIndex);
    heapify(arr, largestIndex, heapSize);
  }
}

const extractMax = (arr) => {
  const maxElement = arr[0];
  arr[0] = arr[arr.length - 1];
  arr.length--;

  heapify(arr, 0, arr.length);

  return maxElement;
}

const buildMaxHeap = (arr) => {
  const lastParentIndex = Math.floor((arr.length - 2) / 2);

  for (let i = lastParentIndex; i >= 0; i--) {
    heapify(arr, i, arr.length);
  }
}

const heapSort = (arr) => {
  // Build the max heap
  buildMaxHeap(arr);

  // Extract the maximum element from the heap and add it to the sorted array
  const sortedArray = [];
  while (arr.length) {
    sortedArray.push(extractMax(arr));
  }
  return sortedArray;
}
```

In this implementation, the `heapSort()` function builds a max heap from the input array using the `buildMaxHeap()` function, then repeatedly extracts the maximum element from the heap using the `extractMax()` function and adds it to the sorted array until the heap is empty. The `heapify()` function maintains the max heap property by comparing the parent node with its child nodes and swapping them if necessary.

### Use

Overall, Heap sort is a highly efficient sorting algorithm with a time complexity of O(n \* log n). It is commonly used in a wide range of applications, such as network routing algorithms, operating systems, and sorting large datasets.

Heap sort is a highly efficient sorting algorithm and is commonly used in various applications where efficient and scalable sorting is required. Some of the common usages of Heap sort are:

1. Operating systems: Heap sort is used in operating systems for process scheduling and memory management. It is often used to maintain a priority queue of processes, where the process with the highest priority is selected first.
    
2. Network routing algorithms: Heap sort is used in network routing algorithms to select the optimal route for data packets. It is often used to maintain a priority queue of routes, where the route with the lowest cost is selected first.
    
3. Sorting large datasets: Heap sort is highly efficient and has a time complexity of O(n log n). It is ideal for sorting large datasets, where other sorting algorithms may become inefficient.
    
4. Database management systems: Heap sort is widely used in database management systems to sort large amounts of data. It is often used for sorting indexes, which helps improve query performance.
    
5. Programming language libraries: Heap sort is implemented in many programming language libraries, such as the C++ standard library and the Java standard library. It is often used as a default sorting algorithm when sorting arrays or lists of elements.
    

### Conclusion

Heap sort is a powerful sorting algorithm that leverages the data structure known as a binary heap to efficiently sort an array. Although it is not as widely used as some of the more common sorting algorithms like quicksort or merge sort, heap sort offers several advantages, including its ability to sort in-place, its guaranteed worst-case time complexity of O(n\*log(n)), and its suitability for certain use cases like sorting priority queues.

However, it's important to note that heap sort also has some drawbacks, such as its relatively slow performance on small datasets and its complexity in implementation compared to other sorting algorithms. Additionally, it requires extra memory to store the heap data structure, which can be a concern in memory-constrained applications.

Despite these considerations, heap sort remains an important sorting algorithm in computer science and is often used as a building block for other algorithms and data structures. By understanding the fundamentals of heap sort and its strengths and weaknesses, developers and engineers can make informed decisions when selecting a sorting algorithm for their applications.

Having this algorithm at the ready is an important tool in your belt for combating these particular use cases. But now you know.