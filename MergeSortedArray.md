https://javascript.plainenglish.io/leetcode-algorithm-series-merge-sorted-array-3ec101aa3cca
I don't really get it.

```javascript
/**
 * @param {number[]} nums1
 * @param {number} m
 * @param {number[]} nums2
 * @param {number} n
 * @return {void} Do not return anything, modify nums1 in-place instead.
 */
var merge = function(nums1, m, nums2, n) {
    nums1.splice(m)
    for (let i = 0; i < n; i++) {
        nums1.push(nums2[i])
    }

    // Sort fixed nums1 in non-decreasing order
    for (let j = 1; j < m+n; j++) {
            if ((nums1[j-1] || nums1[j-1] === 0) && nums1[j] < nums1[j-1]) {
                let tmp = nums1[j-1]
                nums1[j-1] = nums1[j]
                nums1[j] = tmp
                j = j-2
            }
        }
    }
  return nums1
};
```
