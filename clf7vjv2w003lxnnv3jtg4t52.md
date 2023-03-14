---
title: "Sorting with Bubble Sort in JavaScript"
datePublished: Tue Mar 14 2023 06:30:39 GMT+0000 (Coordinated Universal Time)
cuid: clf7vjv2w003lxnnv3jtg4t52
slug: sorting-with-bubble-sort-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/om4O_x_qWD8/upload/6517207fbfccc3941260cbf1207e8ad6.jpeg
tags: algorithms, javascript, coding, sorting, bubble-sort

---

Bubble sort is a simple sorting algorithm to understand. It works by repeatedly swapping adjacent elements if they are in the wrong order.

It starts at the beginning of the array and compares each pair of adjacent elements. If they are in the wrong order (e.g., the first element is greater than the second), it swaps them. It then moves on to the next pair of adjacent elements and repeats the process until it reaches the end of the array.

The name "bubble sort" comes from the fact that smaller elements "bubble" to the top of the list as the algorithm makes its passes through the list.

This process is repeated multiple times until the entire array is sorted. Each pass through the array "bubbles up" the largest unsorted element to its correct position at the end of the array, hence the name "bubble sort". The algorithm has a time complexity of O(n^2), which means that it is not efficient for large datasets.

### Code

Here is a function that Bubble Sorts in JavaScript:

```javascript
const bubbleSort = (array) => { 
    let swapped; 
    do { 
        swapped = false; 
        for (let i = 0; i < array.length - 1; i++) { 
            if (array[i] > array[i + 1]) { 
                let temp = array[i]; 
                array[i] = array[i + 1]; 
                array[i + 1] = temp; 
                swapped = true; 
                } 
            } 
    } 
    while (swapped); 
return array; 
}
```

In this implementation, the `bubbleSort` takes an array of numbers as input and returns a sorted array.

The algorithm starts by setting the swapped variable to false. It then enters a loop that continues until no more swaps are made.

Inside the loop, the algorithm compares adjacent pairs of elements in the array. If they are in the wrong order, it swaps them and sets the swapped variable to true. If no swaps are made during the loop, the swapped variable remains false, and the algorithm exits the loop.

The `bubbleSort` function returns the sorted array.

```javascript
var myArray = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]; 
var sortedArray = bubbleSort(myArray); 
console.log(sortedArray); 
// Output: [1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9]
```

### Use

Bubble sort is not typically used in practical applications because it is not very efficient. However, it can be a good choice for sorting small arrays or for educational purposes to teach the basic concepts of sorting algorithms.

Actually, the most common usage of bubble sort is in computer science education, where it is often used to teach students how sorting algorithms work. By implementing the bubble sort algorithm, students can gain a better understanding of how sorting algorithms operate and can build upon this knowledge to learn more complex algorithms.

Another common usage of bubble sort is in situations where the input data is already nearly sorted because bubble sort has a best-case time complexity of O(n), which means that it is very efficient when the input data is already sorted or nearly sorted. This beats the time of the worst-case scenarios of other much more efficient sorting algorithms which perform quite worse in almost sorted datasets, like merge sort or quick sort.

Bubble sort can also be useful in situations where the input data is very small because it has a low memory overhead and is easy to understand and implement.

### Conclusion

Overall, bubble sort is not a practical choice for sorting large datasets, but it can be useful for small datasets or educational purposes.

But still, having such a cool name never hurts.