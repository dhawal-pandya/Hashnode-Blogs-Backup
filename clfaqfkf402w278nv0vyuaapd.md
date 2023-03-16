---
title: "Sorting with Selection Sort in JavaScript"
datePublished: Thu Mar 16 2023 06:30:39 GMT+0000 (Coordinated Universal Time)
cuid: clfaqfkf402w278nv0vyuaapd
slug: sorting-with-selection-sort-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/0vY082Un2pk/upload/1758e89023204447ab8e8b4b01216a51.jpeg
tags: algorithms, javascript, coding, sorting-algorithms, selection-sort

---

Selection sort is a simple sorting algorithm that works by repeatedly finding the smallest element in an unsorted array and moving it to the front (i.e., the beginning) of the array. This process is repeated for the remaining unsorted elements until the entire array is sorted.

The algorithm works by dividing the input array into two sub-arrays: the sorted sub-array and the unsorted sub-array. Initially, the sorted sub-array is empty, and the unsorted sub-array contains all the elements of the input array.

In each iteration of the algorithm, the smallest element in the unsorted sub-array is identified and swapped with the leftmost element of the unsorted sub-array. This effectively adds the smallest element to the end of the sorted sub-array and reduces the size of the unsorted sub-array by one element. This process is repeated until the entire array is sorted. It is indeed very similar to the Insertion sort

Selection sort has a time complexity of O(n^2) in all cases, which makes it relatively slow for large arrays. However, it is easy to understand and implement, and it can be useful for sorting small arrays or as a stepping stone to more efficient sorting algorithms.

### Code

Here is Selection Sort in JavaScript:

```javascript
const selectionSort = (array) => {
  for (let i = 0; i < array.length - 1; i++) {
    let minIndex = i;
    for (let j = i + 1; j < array.length; j++) {
      if (array[j] < array[minIndex]) {
        minIndex = j;
      }
    }
    if (minIndex !== i) {
      let temp = array[i];
      array[i] = array[minIndex];
      array[minIndex] = temp;
    }
  }
  return array;
}
```

In this implementation, the `selectionSort` function takes an array of numbers as input and returns a sorted array.

The algorithm starts by iterating over the array from the first element (`i = 0`) to the second-to-last element. For each element, it sets the `minIndex` variable to the current index (`i`) and enters a nested loop that iterates over the remaining unsorted elements of the array.

Inside the nested loop, the algorithm checks whether each element is less than the element at the current minimum index (`array[minIndex]`). If it is, the algorithm updates the `minIndex` variable to the index of the new minimum element.

Once the nested loop is finished, the algorithm checks whether the `minIndex` variable has changed. If it has, the algorithm swaps the element at the current index (`array[i]`) with the minimum element at index `minIndex`.

The `selectionSort` function returns the sorted array.

```javascript
var myArray = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5];
var sortedArray = selectionSort(myArray);
console.log(sortedArray);
// Output: [1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9]
```

### Use

Selection sort is a simple and straightforward sorting algorithm, but it is not as efficient as other more complex algorithms like quicksort or mergesort. Therefore, selection sort is not commonly used for sorting large datasets. However, selection sort can be a good choice in some specific situations.

One common usage of selection sort is when memory space is limited. Selection sort has low memory overhead, as it only needs to store a few variables, so it can be a good choice in situations where memory space is limited.

Another common usage of selection sort is when the number of elements in the array is very small. Selection sort has a time complexity of O(n^2), which makes it inefficient for sorting large datasets. However, for small datasets, selection sort can be a good choice, as it has a low overhead and is easy to implement.

Selection sort can also be used as a component in more complex sorting algorithms. For example, some implementations of quicksort use selection sort to sort small sub-arrays, because selection sort performs well on small datasets and has a low overhead.

### Conclusion

Overall, selection sort is not the most efficient sorting algorithm and is not commonly used for sorting large datasets. However, it can be a good choice in specific situations, such as when memory space is limited or when sorting small arrays.