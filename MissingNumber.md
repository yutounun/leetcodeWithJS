level: 5
2nd time

```javascript
var missingNumber = function (nums) {
  const n = nums.length;
  let sum = 0;
  for (num of nums) {
    sum += num;
  }
  return (n * (n + 1)) / 2 - sum;
};
```
