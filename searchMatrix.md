level:
1st time

My solution
time Beats %
space Beats %

```javascript
/**
 * @param {number[][]} matrix
 * @param {number} target
 * @return {boolean}
 */
var searchMatrix = function (matrix, target) {
  const arr = [];
  for (const nums of matrix) {
    for (const num of nums) {
      arr.push(num);
    }
  }
  console.log("arr :", arr);
  const set = new Set(arr);
  return set.has(target);
};
```

Others

```javascript
function searchMatrix(matrix, target) {
  if (!matrix.length || !matrix[0].length) return false;

  let row = 0;
  let col = matrix[0].length - 1;

  while (col >= 0 && row <= matrix.length - 1) {
    if (matrix[row][col] === target) return true;
    else if (matrix[row][col] > target) col--;
    else if (matrix[row][col] < target) row++;
  }

  return false;
}
```
