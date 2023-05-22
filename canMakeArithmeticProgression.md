level:
1st time

My solution
time Beats 42%
space Beats 34%

```javascript
/**
 * @param {number[]} arr
 * @return {boolean}
 */
var canMakeArithmeticProgression = function (arr) {
  // sort elments in a given array → O(nlogn)
  // loop over arr N times
  // get the diff from 1st el to 2nd el and set as constant diff
  // in each loop, check the diff is same as the constant diff
  // if not return false
  arr.sort((a, b) => {
    return a - b;
  });
  let diff = arr[0] - arr[1];
  for (let i = 1; i < arr.length - 1; i++) {
    if (arr[i] - arr[i + 1] !== diff) return false;
  }
  return true;
};
```

Others

```javascript

```
