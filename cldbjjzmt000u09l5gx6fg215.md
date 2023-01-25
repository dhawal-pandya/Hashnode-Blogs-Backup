# Demystifying Diffing Algorithms

Diffing algorithms are used to compare two sets of data and determine the differences between them. This is commonly used in version control systems, such as Git, to identify the changes made to a file or set of files between different versions. It can also be used in other areas such as comparing two versions of a UI, or comparing two sets of data to identify changes.

### React Reconciliation

In the context of React, diffing algorithms are used to determine the changes made to a component's virtual DOM (Document Object Model) and update the actual DOM efficiently.

React uses a process called 'reconciliation' to determine the changes made to a component's virtual DOM, and then updates the actual DOM accordingly.

React uses a specific diffing algorithm, called the "Reconciliation algorithm" to determine the changes made to a component's virtual DOM. This algorithm compares the virtual DOM tree of the previous render with the virtual DOM tree of the current render. It then identifies the differences between the two trees and updates the actual DOM accordingly.

The Reconciliation algorithm starts by comparing the root elements of the previous and current virtual DOM trees. If the root elements are the same, it proceeds to compare their children. If the root elements are different, it replaces the entire subtree of the root element.

When comparing the children, React uses the 'key' property to identify which elements are the same across renders. If the key property is not provided, React uses the index of the element in the children array. This process continues recursively, comparing and updating the virtual DOM tree until the entire tree has been reconciled.

React uses this diffing algorithm to determine the minimal set of changes necessary to update the actual DOM. This allows React to update the actual DOM in an efficient manner, and minimize the number of changes made to the actual DOM.

There are several other types of diffing algorithms, but the most common ones are the Longest Common Subsequence (LCS) algorithm and the Myers algorithm.

### LCS Algorithm

The Longest Common Subsequence (LCS) algorithm is a method used to find the longest sequence of elements that are common to two sets of data. This algorithm is used in several areas such as version control systems, natural language processing, and bioinformatics.

The LCS algorithm compares two sets of data, usually represented as strings or arrays, and finds the longest common subsequence between them. A subsequence is a sequence of elements that appear in the same order in both sets of data, but not necessarily consecutively.

The algorithm starts by creating a matrix, where the rows represent elements of the first set of data and the columns represent elements of the second set of data. The matrix is filled with 0s initially.

For each element in the first set of data, the algorithm compares it with each element in the second set of data. If the elements are the same, the algorithm adds 1 to the value in the corresponding cell in the matrix. If the elements are different, the algorithm takes the maximum value between the cell above and the cell to the left of the current cell and assigns it to the current cell.

After the matrix is filled, the algorithm traces back through the matrix to find the longest common subsequence. The longest common subsequence is found by starting at the bottom-right corner of the matrix and moving up and left, following the path of the largest values.

Here is how we can write the LCS algorithm in JavaScript ourselves:

```javascript
const findLCS = (str1, str2) => {
    const m = str1.length;
    const n = str2.length;
    const dp = Array(m + 1)
                .fill()
                .map(() => Array(n + 1).fill(0)); 
    for (let i = 1; i <= m; i++) { 
        for (let j = 1; j <= n; j++) { 
            if (str1[i - 1] === str2[j - 1]) { 
                dp[i][j] = dp[i - 1][j - 1] + 1;
             } 
            else { 
                dp[i][j] = Math.max(dp[i - 1][j], dp[i][j - 1]); 
            } 
        } 
    } 
    let i = m, j = n; 
    const lcs = []; 
    while (i > 0 && j > 0) { 
        if (str1[i - 1] === str2[j - 1]) { 
            lcs.unshift(str1[i - 1]); 
            i--; 
            j--; 
        } else if (dp[i - 1][j] > dp[i][j - 1]) { 
            i--; 
        } else { 
            j--;
        } 
    } 
    return lcs.join('');
}
```

This implementation takes in two strings, `str1` and `str2`, as input. It creates a matrix `dp` with dimensions `m+1` by `n+1`, where `m` is the length of `str1` and `n` is the length of `str2`. The matrix is filled with 0s initially.

The outer loop iterates through the rows of the matrix and the inner loop iterates through the columns. For each element in the first string `str1`, it compares it with each element in the second string `str2`.

If the elements are the same, the algorithm adds 1 to the value in the corresponding cell in the matrix. If the elements are different, the algorithm takes the maximum value between the cell above and the cell to the left of the current cell and assigns it to the current cell.

After the matrix is filled, the algorithm traces back through the matrix to find the longest common subsequence. It starts at the bottom-right corner of the matrix and moves up and left, following the path of the largest values.

For each step, if the element from `str1` and `str2` are the same, it adds the element to the `lcs` array and moves diagonally up-left on the matrix. If the element from `str1` and `str2` are different, it moves either up or left, depending on the value of the matrix.

Once the tracing back is done, the `lcs` array contains the elements of the longest common subsequence and it's returned as a string by simply joining the array with an empty string.

This example explains the LCS algorithm in JavaScript, it is usually written in faster-executing languages, and also could be optimized for larger inputs and specific use cases.

### Myers Algorithm

The Myers algorithm is a diffing algorithm that uses a dynamic programming approach to find the shortest sequence of edit operations (insertions, deletions, and substitutions) that can be used to transform one set of data into another.

This algorithm is widely used in version control systems, such as Git, to identify the changes made to a file or set of files between different versions.

The Myers algorithm starts by creating a grid of cells, where each cell represents a position in the two sets of data being compared. Each cell contains a value that represents the distance between the two sets of data at that position.

The algorithm then iteratively fills in the grid, starting from the top-left corner and working its way toward the bottom-right corner.

The algorithm uses a series of edit operations to move from one cell to another. These operations include diagonal moves (representing a matching character), vertical moves (representing a deletion), and horizontal moves (representing an insertion).

The distance of a cell is defined as the minimum number of edit operations required to reach that cell. As the algorithm iterates through the grid, it uses the distance of the surrounding cells to calculate the distance of each new cell.

Once the grid is filled, the algorithm traces back through the grid to find the shortest sequence of edit operations that can be used to transform one set of data into the other.

This is done by starting at the bottom-right corner and following the path of the smallest distances, working backward to the top-left corner.

The Myers algorithm is considered to be more efficient than the LCS algorithm in terms of time complexity because it uses a dynamic programming approach that allows it to find the shortest sequence of edit operations more efficiently, thus it's widely used in version control systems like Git.

Here is how we can write the Myers' algorithm in JavaScript ourselves:

```javascript
const findMyersDiff = (a, b) => {
    const N = a.length;
    const M = b.length; 
    const max = N + M; 
    const v = new Array(2 * max + 1); 
    const d = new Array(2 * max + 1); 
    const path = new Array(N + M); 
    for (let i = 0; i < v.length; i++) { 
        v[i] = -1; 
    } 
    v[max + 1] = 0; 
    let x, y; 
    for (let d = 0; d <= max; d++) { 
        for (let k = -d; k <= d; k += 2) { 
            if (k === -d) { 
                x = v[k + max + 1]; 
            } else if (k !== d && v[k - 1 + max] < v[k + 1 + max]) { 
                x = v[k + 1 + max]; 
            } else { 
                x = v[k - 1 + max] + 1; 
            } 
        y = x - k; 
        while (x < N && y < M && a[x] === b[y]) { 
            x++; 
            y++; 
        } 
        if (x >= N && y >= M) { 
            return path; 
        } 
        v[k + max] = x; 
        path[d] = (path[d] || []).concat([[x, y]]); 
        } 
    }
}
```

This implementation takes in two arrays, `a` and `b`, as input. It defines the maximum possible distance `max` as the sum of the lengths of the two input arrays. It creates three arrays `v`, `d`, and `path` with length of `2 * max + 1`*,* `2*max + 1`, and `N+M` respectively.

The outer loop iterates through the distance `d` from 0 to `max`. The inner loop iterates through the value of `k` from `-d` to `d` with a step of 2.

The variables `x` and `y` are used to keep track of the current position on arrays `a` and `b` respectively. `x` starts as the value of `v[k + max + 1]` for the first iteration of `k`, otherwise, it starts as the minimum value between `v[k - 1 + max]` and `v[k + 1 + max] + 1`. `y` is calculated as `x - k`. This is to expect changes between `x` and `y`.

The `while` loop then iterates through the elements of `a` and `b` starting from the current position of `x` and `y` respectively, as long as they are equal. If they are equal, `x` and `y` are incremented.

If `x` and `y` reach the end of their respective arrays, it means that the end of the diffing process has been reached and the `path` array is returned.

The `v` array is updated with the current position of `x` and the path array is updated with the current position of `x` and `y`.

Once the outer loop finishes, it traces back through the `path` array to find the shortest sequence of edit operations that can be used to transform one set of data into the other.

The algorithm would then return the `path` array which contains the sequence of edit operations.

This example explains the Myers algorithm in JavaScript, it is also usually written in faster-executing languages, and also could be optimized for larger inputs and specific use cases.

Myers algorithm is a diffing algorithm that uses a dynamic programming approach to find the shortest sequence of edit operations that can be used to transform one set of data into the other. It's considered to be more efficient than LCS algorithms in terms of time complexity.