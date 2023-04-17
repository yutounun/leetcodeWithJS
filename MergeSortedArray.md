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

My answer that is fast and looks good

```javascript
/**
 * @param {number[]} nums1
 * @param {number} m
 * @param {number[]} nums2
 * @param {number} n
 * @return {void} Do not return anything, modify nums1 in-place instead.
 */
var merge = function (nums1, m, nums2, n) {
  // 1. iterate nums1
  // 2. if it hits 0, replace 0 with nums2.pop()
  // 3. sort nums1 at last
  nums1.sort();
  for (let i = 0; i < m + n; i++) {
    if (nums1[i] === 0 && nums2.length !== 0) {
      nums1[i] = nums2.pop();
    }
  }
  nums1.sort((a, b) => {
    return a - b;
  });
};
```
