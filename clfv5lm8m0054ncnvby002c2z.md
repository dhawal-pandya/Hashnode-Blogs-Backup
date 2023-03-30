---
title: "Searching with Linear Search in JavaScript"
datePublished: Thu Mar 30 2023 13:30:39 GMT+0000 (Coordinated Universal Time)
cuid: clfv5lm8m0054ncnvby002c2z
slug: searching-with-linear-search-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/B-PNrSIU2co/upload/b4a6d599688bcc02dfe3f9ad4788b3ad.jpeg
tags: algorithms, javascript, coding, searching-algorithms, linear-search

---

Linear Search is a simple search algorithm used to find an element in a list of elements.

Linear search is a basic search algorithm to find a specific element in a list or array. It is also known as sequential search, as it searches the elements in sequential order. Linear search works by comparing each element in the list with the target element until a match is found or the end of the list is reached.

The linear search algorithm can be implemented in a straightforward manner using a loop to iterate through each element in the list. At each iteration, the current element is compared with the target element, and if a match is found, the element's index is returned. If the end of the list is reached without finding a match, the algorithm returns a null or negative value to indicate that the element was not found.

It works by sequentially checking each element of the list until a match is found or the entire list has been searched. The time complexity of the linear search algorithm is O(n), where `n` is the number of elements in the list. This means that the worst-case scenario is when the element being searched for is not in the list, and the algorithm has to go through all `n` elements of the list.

### Logic

Here is Linear Search:

* Start at the first element of the list Compare the current element with the target element.
    
* If the current element matches the target element, return the index of the current element.
    
* If the current element does not match the target element, move to the next element in the list and repeat the check.
    
* If the end of the list is reached and the target element has not been found, return -1 to indicate that the target element is not in the list.
    

### Code

Here's the code for Linear Search Algorithm in JavaScript:

```javascript
const linearSearch = (arr, target) => { 
    for (let i = 0; i < arr.length; i++) { 
        if (arr[i] === target) { 
            return i; 
        } 
    } 
    return -1; 
};
```

The `linearSearch` function takes in two parameters, `arr`, which is the list of elements to be searched, and `target`, which is the element that we are looking for. The function then uses a for loop to iterate through the list of elements, comparing each element with the target element using the `===` operator.

```javascript
const myArray = [3, 1, 4, 1, 5]; 
const target = 4; 
const result = linearSearch(myArray, target); 
console.log(result); // Output: 2
```

### Use

Linear search has several uses in computer programming and data analysis. Here are a few examples:

1. Searching unsorted or small datasets: Linear search is useful when searching through a small dataset or a list that is not sorted. In such cases, the overhead of sorting the data using other algorithms may not be justified.
    
2. Implementing other search algorithms: Linear search can be used as a building block for more complex search algorithms. For example, in certain cases, a binary search may not be possible or practical, and linear search can be used as a fallback option.
    
3. Debugging code: Linear search can be used to verify that a particular item is or is not in a given list. This is useful when debugging code to ensure that data is being properly processed.
    

Overall, linear search is a simple and straightforward algorithm that can be used in a variety of applications. While it may not be the most efficient search algorithm for large datasets, it can be useful in situations where other algorithms are not suitable or practical.

### Conclusion

Linear search has a time complexity of O(n), where n is the number of elements in the list. This means that the time it takes to perform a linear search increases linearly with the size of the list. Linear search is simple to understand and implement, but it may be inefficient for large datasets, as the entire list must be searched even if the target element is at the beginning of the list.

Despite its limitations, linear search is still useful in certain scenarios, such as when the list is small or when the elements are not sorted in any particular order. It is also a useful starting point for understanding more complex search algorithms.