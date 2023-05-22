level:
1st time

My solution
Time complexity Beats: 53.21%
Space complexity Beats: 94.50%

```javascript
/**
 * @param {number[][]} grid
 * @param {number} k
 * @return {number[][]}
 */
var shiftGrid = function (grid, k) {
  for (let i = 0; i < k; i++) {
    for (let j = 0; j < grid.length; j++) {
      const row = grid[j];
      const splicedVal = row.pop();
      // last row
      if (j === grid.length - 1) {
        grid[0].unshift(splicedVal);
      } else {
        grid[j + 1].unshift(splicedVal);
      }
    }
  }
  return grid;
};
```

Others

```javascript

```
