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
    for (let col = 0; col < row; col++) {
      // Push 1 into first and last el of arr. Set 1 at the both edge of an array.
      if (col === 0 || col === row - 1) {
        arr.push(1);
      } else {
        // Since row starts from 1,
        // you need to substract 2 from row to get last element.
        arr.push(result[row - 2][col - 1] + result[row - 2][col]);
      }
    }
    result.push(arr);
  }
  return result;
};
```
