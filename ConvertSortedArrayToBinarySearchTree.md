https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/description/

```javascript
/**
 * @param {number[]} nums
 * @return {TreeNode}
 */
var sortedArrayToBST = function (nums) {
  if (!nums.length) return null;
  // In the Example1 case, this indicates index of 2 meaning a number of 0.
  const mid = Math.floor(nums.length / 2);
  const root = new TreeNode(nums[mid]);

  // subtrees are BSTs as well
  root.left = sortedArrayToBST(nums.slice(0, mid));
  // Splice nums[mid+1] to last num of nums
  root.right = sortedArrayToBST(nums.slice(mid + 1));

  // root : [-10]
  // root : [-3,-10]
  // root : [5]
  // root : [9,5]
  // root : [0,-3,9,-10,null,5]
  console.log("root :", root);
  return root;
};
```
