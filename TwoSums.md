https://leetcode.com/problems/two-sum/

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function (nums, target) {
  const map = {};

  for (let i = 0; i < nums.length; i++) {
    const currentNum = nums[i];
    const neededNum = target - nums[i];
    if (map[currentNum] === undefined) {
      map[neededNum] = i;
    } else {
      return [map[currentNum], i];
    }
  }
};
```
