level: 5
2nd time

```javascript
/**
 * @param {number} n
 * @return {boolean}
 */
var isPowerOfThree = function (n) {
  // iterate using while untill n won't be splited by 3
  // split n by 3 in each loop
  // return true if n = 1
  if (n <= 0) return false;
  while (n % 3 === 0) {
    n = n / 3;
  }
  return n === 1;
};
```
