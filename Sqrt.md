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
