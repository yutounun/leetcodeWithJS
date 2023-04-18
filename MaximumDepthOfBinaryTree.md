https://leetcode.com/problems/maximum-depth-of-binary-tree/description/
2nd time

```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number}
 */
var maxDepth = function (root) {
  // In case a node doesn't have any child nodes
  if (!root) return 0;

  // If a node doesn't have any child nodes, the next line will return only 1.
  // If it does, this return how many child nodes it has + 1(itself)
  return 1 + Math.max(maxDepth(root.left), maxDepth(root.right));
};
```
