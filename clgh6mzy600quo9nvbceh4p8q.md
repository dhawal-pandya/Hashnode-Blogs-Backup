---
title: "Solving Two Sum"
datePublished: Fri Apr 14 2023 23:30:39 GMT+0000 (Coordinated Universal Time)
cuid: clgh6mzy600quo9nvbceh4p8q
slug: solving-two-sum
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/gdL-UZfnD3I/upload/c0eb0555b36dfcfde9c5bbca15cde0b6.jpeg
tags: algorithms, data-structures, solution, dsa, two-sum

---

I can't solve the partner problem for you, we can at least code the approximation, can't we? The Two Sum question is one that has been known to trip up many a programmer, and yet it is deceptively simple.

### The Premise

The question asks you to find two numbers in an array that add up to a target value. While the question may seem straightforward, the devil is in the details.

The Two Sum question can be phrased differently, but the general idea is the same. Given an array of numbers and a target value, find two numbers in the array that add up to the target value.

For example, if the array is \[2, 7, 11, 15\] and the target value is 9, the answer is \[2, 7\]. There are many different approaches to solving this problem, but we will focus on the brute-force approach and optimize it from there.

### Noob Solution

The brute-force approach is to loop through each element in the array and check if there is another element that adds up to the target value. If we find such a pair, we return it. Otherwise, we continue looping until we have checked every possible pair.

Here is the less optimized but intuitive logic:

In JS:

```javascript
function twoSum(nums, target) {
  for (let i = 0; i < nums.length; i++) {
    for (let j = i + 1; j < nums.length; j++) {
      if (nums[i] + nums[j] === target) {
        return [i, j];
      }
    }
  }
  return [];
```

In Python:

```javascript
def twoSum(nums, target):
    for i in range(len(nums)):
        for j in range(i+1, len(nums)):
            if nums[i] + nums[j] == target:
                return [i, j]
    return []
```

This code block works by looping through each element in the array and checking if there is another element that adds up to the target value. If we find such a pair, we return it. Otherwise, we continue looping until we have checked every possible pair. This approach works, but it has a time complexity of O(n^2), which means it will be slow for large arrays.

### Pro Solution

To optimize this approach, we can use a hash table to store the values we have already seen. We loop through the array once, checking if the complement of the current number (i.e., the difference between the target value and the current number) is already in the hash table. If it is, we return the indices of the current number and its complement. Otherwise, we add the current number and index to the hash table and continue looping.

Here is the optimized code block:

In JS:

```javascript
function twoSum(nums, target) {
  const hash = {};
  for (let i = 0; i < nums.length; i++) {
    const complement = target - nums[i];
    if (complement in hash) {
      return [hash[complement], i];
    }
    hash[nums[i]] = i;
  }
  return [];
}
```

In Python:

```javascript
def twoSum(nums, target):
    hash = {}
    for i, num in enumerate(nums):
        complement = target - num
        if complement in hash:
            return [hash[complement], i]
        hash[num] = i
    return []
```

This optimized code block has a time complexity of O(n), which means it is much faster than the brute-force approach.

We achieve this speedup by sacrificing space complexity, as we now need to store the values we have seen in a hash table. However, this tradeoff is worth it, as the optimized approach is much more efficient for large arrays.

There are a few other ways to do it, but always remember to write code that is more readable, rather than some code that is very fast, but obscure beyond legibility.

### Conclusion

The Two Sum question is a deceptively simple problem that can be solved in many ways. We explored the brute-force approach and the optimized approach using a hash table. While the brute-force approach works, it is slow for large arrays. The optimized approach, on the other hand, is much faster and has a time complexity of O(n).

By understanding the tradeoffs between time and space complexity, we can write more efficient code and solve problems more effectively. We can begin becoming better coders.