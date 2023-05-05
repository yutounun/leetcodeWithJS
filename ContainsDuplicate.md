level: 1
2nd time

The smartest solution

```javascript
function setSolution(nums) {
  let testSet = new Set(nums);
  return testSet.size !== nums.length;
}
```

```javascript
/**
 * @param {number[]} nums
 * @return {boolean}
 */
var containsDuplicate = function (nums) {
  const map = {};
  for (const num of nums) {
    if (map[num]) {
      return true;
    } else {
      map[num] = 1;
    }
  }
  return false;
};
```
