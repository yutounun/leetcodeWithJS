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
 * @return {boolean}
 */
var isUnivalTree = function (root) {
  const value = root.val;
  function traversalCheck(node) {
    if (node === null) {
      return true;
    }
    if (value !== node.val) {
      return false;
    }
    const left = node.left;
    const right = node.right;
    // if the value of the child node is same as "value" return false
    // if the child node is null return true,
    // even though left or right node is missing, another node is same as "value", return true on next code
    return traversalCheck(left) && traversalCheck(right);
  }
  return traversalCheck(root);
};
```
