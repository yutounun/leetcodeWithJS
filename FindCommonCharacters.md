level: 5
1st time

```javascript
/**
 * @param {string[]} A
 * @return {string[]}
 */
var commonChars = function (A) {
  let res = [...A[0]];
  console.log("res1 :", res);
  // Start iterating from the second string in the array
  for (let i = 1; i < A.length; i++) {
    res = res.filter((c) => {
      const len = A[i].length;
      A[i] = A[i].replace(c, "");
      return len > A[i].length;
    });
    console.log("res in each loop :", res);
  }
  return res;
};
```
