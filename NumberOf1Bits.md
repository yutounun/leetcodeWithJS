level: 2
1st time

```javascript
/**
 * @param {number} n - a positive integer
 * @return {number}
 */
var hammingWeight = function (n) {
  // iterate the given n 32 times
  // In the loop if n&1 is 1, add 1 to count variable
  // shift n to right
  let count = 0;
  for (let i = 0; i < 32; i++) {
    if (n & (1 === 1)) count++;
    n >>= 1;
  }
  return count;
};
```
