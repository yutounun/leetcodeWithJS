https://leetcode.com/problems/pascals-triangle/description/
https://dev.to/alisabaj/solving-pascal-s-triangle-in-javascript-4e59

```javascript
const generate = function (numRows) {
  // initialize an rtnArray
  // iterate numRows times
  // initialize an array with 1 element inside a loop
  // iterate 2nd array i times
  // push [i-1][j-1]+[i-1][j] into the array
  // add 1 at the last
  const rtnArr = [];
  for (let i = 0; i < numRows; i++) {
    const tmpArr = [1];
    if (i > 1) {
      for (let j = 1; j < i; j++) {
        // rtnArr[1][0] + rtnArr[1][1]
        tmpArr.push(rtnArr[i - 1][j - 1] + rtnArr[i - 1][j]);
      }
    }
    if (i > 0) {
      tmpArr.push(1);
    }
    // console.log("tmpArr: ",tmpArr)
    rtnArr.push(tmpArr);
  }
  return rtnArr;
};
```
