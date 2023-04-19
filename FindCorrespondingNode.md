1st time
level: 6

```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} original
 * @param {TreeNode} cloned
 * @param {TreeNode} target
 * @return {TreeNode}
 */

var getTargetCopy = function (original, cloned, target) {
  // Find target value in cloned node using some algorithm
  function findTarget(root) {
    if (!root) return null;
    if (root.val === target.val) return root;
    const left = findTarget(root.left);
    if (left) return left;
    return findTarget(root.right);
  }
  return findTarget(cloned);
};
```
