https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/

```javascript
const maxProfit = (prices) => {
  // initialize min and maxProfit
  // iterate a given array
  // update min and maxProfit if neccesary

  let min = Infinity;
  let maxProfit = 0;
  for (const price of prices) {
    if (price < min) {
      min = price;
    }
    const sub = price - min;
    if (sub > maxProfit) {
      maxProfit = sub;
    }
  }
  return maxProfit;
};
```
