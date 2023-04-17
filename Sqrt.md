2nd time
level: 2

Better suggested solution

```javascript
var mySqrt = function (x) {
  // Find an integer that makes x by multiplying same integer
  let root = 1;
  while (true) {
    if (x < root * root) {
      return root - 1;
    } else {
      root += 1;
    }
  }
};
```

My following code needs to be optimized.

```javascript
/**
 * @param {number} x
 * @return {number}
 */
var mySqrt = function (x) {
  if (x === 0) return 0;
  if (x < 4) return 1;

  for (let i = 0; i <= x / 2; i++) {
    if (i * i === x) {
      return i;
    } else if (i * i < x && (i + 1) * (i + 1) > x) {
      return i;
    }
  }
};
```
