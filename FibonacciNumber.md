level:2
1st time

Better solution

```javascript
var fib = function (n) {
  if (n < 2) return n;
  let a = 0,
    b = 1;
  for (let i = 1; i < n; i++) [a, b] = [b, a + b];
  return b;
};
```

my solution

```javascript
/**
 * @param {number} n
 * @return {number}
 */
var fib = function (n) {
  if (n < 1) return 0;
  const ans = [1];
  let prev = 1;
  let prevPrev = 0;
  for (let i = 0; i < n; i++) {
    const current = prev + prevPrev;
    ans.push(current);
    prevPrev = prev;
    prev = current;
  }
  return ans[n - 1];
};
```
