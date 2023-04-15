https://leetcode.com/problems/two-sum/

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    //ex: [{2: 0}, {7: 1}...]
    const map = new Map();

    for(let i = 0; i<nums.length; i++) {
        const currentNum = nums[i]
        const neededNum = target - currentNum
        if (map.has(neededNum)) {
            return [map.get(neededNum), i]
        } else {
            map.set(currentNum, i)
        }
    }
};
};
```
