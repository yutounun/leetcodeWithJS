level: 3
1st time

My solution

```javascript
/**
 * @param {number} n
 * @return {number}
 */
var tribonacci = function (n) {
  if (n < 2) return n;
  if (n === 2) return 1;

  let prev = 1;
  let prevPrev = 1;
  let prevPrevPrev = 0;
  let current = 2;

  for (let i = 3; i < n + 1; i++) {
    current = prevPrevPrev + prevPrev + prev;
    prevPrevPrev = prevPrev;
    prevPrev = prev;
    prev = current; // current
  }
  return prev;
};
// 0, 1, 1, 2, 4, 7(index: 5)
```

Others

```javascript

```
