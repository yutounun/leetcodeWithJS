https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/

```javascript
const maxProfit = (prices) => {
  let left = 0; // Buy
  let right = 1; // sell
  let max_profit = 0;

  while (right < prices.length) {
    // In case you can gain any profit.
    if (prices[left] < prices[right]) {
      let profit = prices[right] - prices[left]; // our current profit

      max_profit = Math.max(max_profit, profit);
    } else {
      // If you cannot gain any profit.
      left = right;
    }
    right++;
  }
  return max_profit;
};
```
