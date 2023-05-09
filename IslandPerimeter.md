1st time
level: 3

```javascript
/**
 * @param {number[][]} grid
 * @return {number}
 */
var islandPerimeter = function (grid) {
  let sum = 0;
  for (let row = 0; row < grid.length; row++) {
    for (let col = 0; col < grid[row].length; col++) {
      const currentVal = grid[row][col];
      if (currentVal === 1) {
        sum += 4;
      }
      if (grid[row]?.[col - 1] === 1) {
        sum--;
      }
      if (grid[row - 1]?.[col - 1] === 1) {
        sum--;
      }
      if (grid[row - 1]?.[col] === 1) {
        sum--;
      }
      console.log("sum :", sum);
    }
  }
  return sum;
};
```
