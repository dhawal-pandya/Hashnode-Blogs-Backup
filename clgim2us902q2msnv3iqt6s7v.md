---
title: "Solving Best Time To Buy and Sell Stock"
datePublished: Sat Apr 15 2023 23:30:39 GMT+0000 (Coordinated Universal Time)
cuid: clgim2us902q2msnv3iqt6s7v
slug: solving-best-time-to-buy-and-sell-stock
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/fiXLQXAhCfk/upload/fee43c663d3e1be522d4d0d274a223de.jpeg
tags: algorithms, data-structures, solution, dsa, best-time-to-buy-and-sell-stocks

---

The Best Time to Buy and Sell Stocks is a classic coding problem that asks the programmer to determine the maximum profit that can be made by buying and selling a stock over a given period of time. The problem is defined by an array of stock prices, where each element represents the price of the stock on a particular day. The task is to find the maximum profit that can be made by buying and selling the stock at any point in time within the given period.

### The Premise

The premise of the Best Time to Buy and Sell Stocks question is to find the maximum profit that can be obtained by buying and selling a stock at the right time, given an array of historical stock prices. The array represents the prices of the stock on different days, where each element of the array represents the price of the stock on a given day.

The question assumes that an investor can only buy and sell a single stock and must buy before selling. Additionally, the investor cannot short-sell the stock, i.e., the investor can only make a profit by buying the stock at a lower price and selling it at a higher price.

The goal of the question is to develop an algorithm that can efficiently find the maximum profit that can be obtained by buying and selling a stock at the right time, given the historical prices of the stock. The algorithm must run in O(n) time complexity, where n is the length of the array.

### Noob Solution

The naive or intuitive approach to solve this problem would be to use two nested loops. The outer loop iterates through the array of stock prices, and the inner loop iterates from the current index to the end of the array, checking for the maximum difference between the prices at the current index and each subsequent index. While this approach is easy to understand and implement, it has a time complexity of O(n^2) and is hence not suitable for large input sizes.

Here's an example of the less optimized, intuitive code block.

In JS:

```javascript
const maxProfit = (prices) => {
  let maxProfit = 0;
  for (let i = 0; i < prices.length; i++) {
    for (let j = i + 1; j < prices.length; j++) {
      const profit = prices[j] - prices[i];
      if (profit > maxProfit) {
        maxProfit = profit;
      }
    }
  }
  return maxProfit;
}
```

In Python:

```python
def max_profit(prices):
    max_profit = 0
    for i in range(len(prices)):
        for j in range(i+1, len(prices)):
            profit = prices[j] - prices[i]
            if profit > max_profit:
                max_profit = profit
    return max_profit
```

### Pro Solution

A more optimized approach to solving this problem involves using a single loop and keeping track of the minimum stock price seen so far and the maximum profit that can be made from that minimum price. This approach has a time complexity of O(n) and is much more efficient than the previous approach.

Here's an example of the optimized code:

In JavaScript:

```javascript
const maxProfit = (prices) => {
  let minPrice = Infinity;
  let maxProfit = 0;
  for (let i = 0; i < prices.length; i++) {
    if (prices[i] < minPrice) {
      minPrice = prices[i];
    } else if (prices[i] - minPrice > maxProfit) {
      maxProfit = prices[i] - minPrice;
    }
  }
  return maxProfit;
}
```

In Python:

```python
def max_profit(prices):
    min_price = float('inf')
    max_profit = 0
    for price in prices:
        if price < min_price:
            min_price = price
        elif price - min_price > max_profit:
            max_profit = price - min_price
    return max_profit
```

In the optimized solution, we keep track of the minimum price seen so far in the `min_price` variable and update it whenever we encounter a lower price. We also keep track of the maximum profit that can be made from that minimum price in the `max_profit` variable and update it whenever we encounter a higher price.

### Conclusion

The Best Time to Buy and Sell Stocks question is an important problem in the field of algorithmic trading and finance. In the stock market, investors are always looking for opportunities to make profits by buying stocks at a lower price and selling them at a higher price. This question asks to find the maximum profit that can be obtained by buying and selling a stock at the right time, given an array of historical stock prices.

Solving this question can provide valuable insights into the behavior of the stock market and can be used to develop trading strategies. Additionally, this question is commonly asked in technical interviews for software engineering roles and is a good indicator of a candidate's ability to think critically and solve algorithmic problems.