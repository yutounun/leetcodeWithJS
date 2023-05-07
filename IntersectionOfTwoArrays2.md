level: 3
2nd time

```javascript
/**
 * @param {number[]} nums1
 * @param {number[]} nums2
 * @return {number[]}
 */
var intersect = function (nums1, nums2) {
  const map = {};
  const ans = [];
  for (const num of nums1) {
    if (!map[num]) {
      map[num] = 1;
    } else {
      map[num]++;
    }
  }
  for (const num of nums2) {
    if (map[num]) {
      map[num]--;
      ans.push(num);
    }
  }
  return ans;
};
```
