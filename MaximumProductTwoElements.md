level:
1st time

My solution

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var maxProduct = function (nums) {
  // find two of the largest numbers from nums
  // time complexity: O(n)
  // space: O(2) → O(1)
  nums.sort((a, b) => {
    return a - b;
  });
  const biggest = nums[nums.length - 1];
  const big = nums[nums.length - 2];
  return (biggest - 1) * (big - 1);
};
```

Others

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var maxProduct = function (nums) {
  // find the largest numbers from nums
  // time complexity: O(n)
  // space: O(1) for constant values
  let max1 = 0,
    max2 = 0;
  for (const num of nums) {
    if (num > max1) {
      max2 = max1;
      max1 = num;
    } else if (num > max2) {
      max2 = num;
    }
  }
  return (max1 - 1) * (max2 - 1);
};
```
