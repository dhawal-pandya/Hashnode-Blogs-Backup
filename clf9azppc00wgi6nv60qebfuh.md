---
title: "Sorting with Insertion Sort in JavaScript"
datePublished: Wed Mar 15 2023 06:30:39 GMT+0000 (Coordinated Universal Time)
cuid: clf9azppc00wgi6nv60qebfuh
slug: sorting-with-insertion-sort-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/MfnX4XtGnvU/upload/3e4d7d98f91d97a5379e9e4bc2dbb6ea.jpeg
tags: algorithms, javascript, coding, insertion-sort, sorting

---

Insertion sort is a simple sorting algorithm that builds the final sorted array one item at a time. It works by repeatedly taking an element from the unsorted portion of the array and inserting it into the correct position in the sorted portion of the array. It iterates over an unsorted array of items and inserts each element into its proper position in a growing sorted list until the entire array is sorted.

The algorithm starts by considering the first element of the array as the only element in the sorted list. Then, it takes the next unsorted element and inserts it into its proper position in the sorted list, shifting other elements if necessary. It continues this process for each remaining unsorted element until the entire array is sorted.

Insertion sort is similar to how you might sort a hand of playing cards. You start with one card and then insert each subsequent card into its proper position relative to the cards you've already sorted.

### Code

Here is Insertion Sort in JavaScript:

```javascript
const insertionSort = (array) => {
  for (let i = 1; i < array.length; i++) {
    let current = array[i];
    let j = i - 1;
    while (j >= 0 && array[j] > current) {
      array[j + 1] = array[j];
      j--;
    }
    array[j + 1] = current;
  }
  return array;
}
```

In this implementation, the `insertionSort` function takes an array of numbers as input and returns a sorted array.

The algorithm starts by iterating over the array from the second element (`i = 1`) to the last element. For each element, it saves the value in the `current` variable and sets `j` to the index of the previous element (`i - 1`).

The algorithm then enters a loop that continues as long as `j` is greater than or equal to 0 and the element at index `j` is greater than `current`. Inside the loop, the algorithm shifts the element at index `j` one position to the right, which makes space for `current`. It then decrements `j` so that the algorithm can compare `current` to the next element to the left.

Once the loop is finished, the algorithm inserts `current` into the correct position in the sorted portion of the array. It does this by setting the element at index `j + 1` to `current`.

The `insertionSort` function returns the sorted array.

```javascript
var myArray = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5];
var sortedArray = insertionSort(myArray);
console.log(sortedArray);
// Output: [1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9]
```

### Use

Insertion sort is a simple sorting algorithm that is not as efficient as more complex algorithms like quicksort or mergesort, so it is not commonly used for sorting large datasets. However, insertion sort can be a good choice in some specific situations.

One common usage of insertion sort is when the input data is already nearly sorted, just like bubble sort. In this case, insertion sort can perform very well, with a time complexity of O(n) in the best-case scenario where the input data is already sorted.

Insertion sort can also be used when sorting small arrays or when the number of elements in the array is very small. Insertion sort also has a low memory overhead like bubble sort and is easy to implement, so it can be a good choice for sorting small arrays where the efficiency of the algorithm is not critical.

Another common usage of insertion sort is as a component in more complex sorting algorithms. For example, some implementations of quicksort use insertion sort to sort small sub-arrays, because insertion sort performs well on small datasets and has a low overhead.

### Conclusion

Overall, insertion sort is not the most efficient sorting algorithm and is not commonly used for sorting large datasets. However, it can be a good choice in specific situations, such as when the input data is already nearly sorted, or when sorting small arrays.

Its name does make sense now, doesn't it?