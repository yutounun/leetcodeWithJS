https://leetcode.com/problems/pascals-triangle/description/
https://dev.to/alisabaj/solving-pascal-s-triangle-in-javascript-4e59

I haven't understand how this solution works at all.

```javascript
/**
 * @param {number} numRows
 * @return {number[][]}
 */
const generate = function (numRows) {
  if (numRows === 0) return [];
  if (numRows === 1) return [[1]];
  let result = [];
  for (let row = 1; row <= numRows; row++) {
    let arr = [];
    // In the first loop, the following loop does only one loop.
    // The number of row and the number of elements in that array is same.
    for (let col = 0; col < row; col++) {
      // Push 1 into first and last el of arr
      if (col === 0 || col === row - 1) {
        arr.push(1);
      } else {
        arr.push(result[row - 2][col - 1] + result[row - 2][col]);
      }
    }
    result.push(arr);
  }
  return result;
};
```
