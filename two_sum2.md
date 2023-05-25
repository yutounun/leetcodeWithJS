level:
1st time

My solution
time Beats %
space Beats %

```javascript
/**
 * @param {number[]} numbers
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function (nums, target) {
  const obj = {};
  for (let i = 0; i < nums.length; i++) {
    const num = nums[i];
    if (obj[num] !== undefined) {
      return [obj[num] + 1, i + 1];
    } else {
      obj[target - num] = i;
    }
  }
};
```

Others

```javascript
var twoSum = function (numbers, target) {
  numbers.sort((a, b) => a - b);
  let left = 0;
  let right = numbers.length - 1;

  while (left < right) {
    const sum = numbers[left] + numbers[right];
    if (sum === target) {
      // Adding 1 because the problem is 1-indexed
      return [left + 1, right + 1];
    } else if (sum < target) {
      left++;
    } else {
      right--;
    }
  }

  return [];
};
```
