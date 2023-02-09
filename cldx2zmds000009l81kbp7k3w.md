# Demystifying Big O Notations (2/2)

I'd like to give some concrete examples of how to use and apply all the mumbo jumbo I said in the last post, so here we go.

The most common big O notations used are:

* O(1) - Constant Time: This notation represents an algorithm that takes a constant amount of time to run, regardless of the size of the input. An example of an O(1) algorithm is accessing an element in an array using an index.
    
* O(log n) - Logarithmic Time: This notation represents an algorithm that takes logarithmic time to run. Logarithmic algorithms are efficient for large inputs, as the growth rate of their running time is relatively slow. An example of an O(log n) algorithm is a binary search.
    
* O(n) - Linear Time: This notation represents an algorithm that takes linear time to run. The running time of an O(n) algorithm grows linearly with the size of the input. An example of an O(n) algorithm is linear search.
    
* O(n log n) - Log-Linear Time: This notation represents an algorithm that takes log-linear time to run. The running time of an O(n log n) algorithm grows faster than O(log n) but slower than O(n). An example of an O(n log n) algorithm is merge sort.
    
* O(n^2) - Quadratic Time: This notation represents an algorithm that takes quadratic time to run. The running time of an O(n^2) algorithm grows rapidly with the size of the input. An example of an O(n^2) algorithm is bubble sort.
    
* O(2^n) - Exponential Time: This notation represents an algorithm that takes exponential time to run. The running time of an O(2^n) algorithm grows extremely rapidly with the size of the input. An example of an O(2^n) algorithm is generating all subsets of a given set or the brute-force solution for the traveling salesman problem.
    
* O(n!) - Factorial Time: This notation represents an algorithm that takes factorial time to run. The running time of an O(n!) algorithm grows even faster than O(2^n). An example of an O(n!) algorithm is the brute-force solution for the n-queens problem.
    

These were the most common big O notations. Now let's look at exact examples of them.

### O(1) - Constant Time: Accessing an element in an array using an index.

```javascript
const array = [1, 2, 3, 4, 5];

// Accessing an element in an array using an index is O(1)
console.log(array[2]); // 3
```

### O(log n) - Logarithmic Time: Binary search.

```javascript
const array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

// Binary search algorithm
const binarySearch = (array, target) => {
    let start = 0;
    let end = array.length - 1;
    while (start <= end) {
        const middle = Math.floor((start + end) / 2);
        if (array[middle] === target) {
            return middle;
        } else if (array[middle] < target) {
            start = middle + 1;
        } else {
            end = middle - 1;
        }
    }
    return -1;
};
// Searching for an element in an array using binary search is O(log n)

console.log(binarySearch(array, 7)); // 6
```

### O(n) - Linear Time: Linear search.

```javascript
const array = [1, 2, 3, 4, 5];

// Linear search algorithm
const linearSearch = (array, target) => {
    for (let i = 0; i < array.length; i++) {
        if (array[i] === target) {
            return i;
        }
    }
    return -1;
};

// Searching for an element in an array using linear search is O(n)
console.log(linearSearch(array, 3)); // 2
```

### O(n^2) - Quadratic Time: Bubble sort.

```javascript
const array = [5, 4, 3, 2, 1];

// Bubble sort algorithm
const bubbleSort = array => {
    for (let i = 0; i < array.length; i++) {
        for (let j = 0; j < array.length - i - 1; j++) {
            if (array[j] > array[j + 1]) {
                [array[j], array[j + 1]] = [array[j + 1], array[j]];
            }
        }
    }
    return array;
};

// Sorting an array using bubble sort is O(n^2)
console.log(bubbleSort(array)); // [1, 2, 3, 4, 5]
```

### O(2^n) - Exponential Time: Generating all subsets of a set.

```javascript
const set = [1, 2, 3];

// Function to generate all subsets of a set
const generateSubsets = (set, subset = [], index = 0) => {
  console.log(subset);
  for (let i = index; i < set.length; i++) {
    generateSubsets(set, [...subset, set[i]], i + 1);
  }
};

// Generating all subsets of a set is O(2^n)
generateSubsets(set);
```

Or... the Traveling Salesman Problem

```javascript
const cities = [
  { x: 0, y: 0 },
  { x: 0, y: 1 },
  { x: 1, y: 0 },
  { x: 1, y: 1 }
];

// Function to calculate the distance between two cities
const distance = (cityA, cityB) =>
  Math.sqrt(Math.pow(cityA.x - cityB.x, 2) + Math.pow(cityA.y - cityB.y, 2));

// Function to generate all permutations of cities
const generatePermutations = (cities, permutation = [], used = new Set()) => {
  if (permutation.length === cities.length) {
    console.log(permutation);
    return;
  }

  for (let i = 0; i < cities.length; i++) {
    if (used.has(i)) {
      continue;
    }
    used.add(i);
    generatePermutations(cities, [...permutation, cities[i]], used);
    used.delete(i);
  }
};

// Function to solve the traveling salesman problem
const solveTSP = cities => {
  let minDistance = Infinity;
  generatePermutations(cities, [], new Set());
};

// The brute-force solution for the traveling salesman problem is O(2^n)
solveTSP(cities);
```

### O(n!) - Factorial Time: Generating all permutations of a set.

```javascript
const set = [1, 2, 3];

// Function to generate all permutations of a set
const generatePermutations = (set, permutation = []) => {
  if (!set.length) {
    console.log(permutation);
  }
  for (let i = 0; i < set.length; i++) {
    const newSet = [...set.slice(0, i), ...set.slice(i + 1)];
    const newPermutation = [...permutation, set[i]];
    generatePermutations(newSet, newPermutation);
  }
};

// Generating all permutations of a set is O(n!)
generatePermutations(set);
```

or...the N-Queens Problem

```javascript
// n-queens problem solution
const n = 8;

// Function to check if a queen can be placed at (row, col)
const isSafe = (board, row, col) => {
  // Check this row on left side
  for (let i = 0; i < col; i++) {
    if (board[row][i]) {
      return false;
    }
  }

  // Check upper diagonal on left side
  for (let i = row, j = col; i >= 0 && j >= 0; i--, j--) {
    if (board[i][j]) {
      return false;
    }
  }

  // Check lower diagonal on left side
  for (let i = row, j = col; i < n && j >= 0; i++, j--) {
    if (board[i][j]) {
      return false;
    }
  }
  return true;
};

// Function to solve the n-queens problem
const solveNQueens = col => {
  if (col >= n) {
    return true;
  }

  for (let i = 0; i < n; i++) {
    if (isSafe(board, i, col)) {
      board[i][col] = 1;
      if (solveNQueens(col + 1)) {
        return true;
      }
      board[i][col] = 0;
    }
  }
  return false;
};

// Initializng the board
const board = Array(n)
  .fill()
  .map(() => Array(n).fill(0));

// The brute-force solution for the n-queens problem is O(n!)
console.log(solveNQueens(0));
```

Here were some examples of Big O notations and how they translate into code.

Now no longer shall Big O of any sort trouble you.

Not continued in the next post...