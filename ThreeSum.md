level:
1st time

My solution
time Beats 88%
space Beats 27%

```javascript
/**
 * @param {number[]} nums
 * @return {number[][]}
 */
var threeSum = function(nums) {
    nums.sort((a, b)=> {
        return a - b
    })
    // [-4, -1, -1, 0, 1, 2]
    let target = 0
    const ans = []

    for (let i = 0; i < nums.length - 2; i++) {
        const num = nums[i]
        // positive numbers cannot sum to a negative number
        // if num is positive number such as 1, two of other nums are also positive
        // meaning sum of those nums can never be 0
        // quit iterating when num is positive
        if (num > target) break

        // Skip this iteration when the current number is the same as the previous one.
        if (num === nums[i - 1]) continue

        // start two sum Ⅱ down to this point
        // no need to set 0 to left to improve performance
        let left = i + 1
        let right = nums.length - 1

        while (left < right) {
            const sum = num + nums[left] + nums[right]
            if (sum === target) {
                ans.push([num, nums[left], nums[right]])

                // skip duplicated nums 
                // to avoid to return the same array in the ans
                // if the input array is [-1, 0, 1, 1, 1, -1, -1, -1], 
                // the function could return [-1, 0, 1] multiple times
                while (nums[left] === nums[left + 1]) left++
				while (nums[right] === nums[right - 1]) right--

				left++
				right--
            } else if (sum > target) {
                right--
            } else {
                left++
            }
        }
    }
    return ans
    
};
```

Others

```javascript

```
