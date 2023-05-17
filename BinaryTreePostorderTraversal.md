level: 5
1st time

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
 * @return {number[]}
 */
var postorderTraversal = function (root) {
  const ans = [];
  function traverse(node) {
    if (!node) return true;
    traverse(node.left);
    traverse(node.right);
    ans.push(node.val);
  }
  traverse(root);
  console.log("ans :", ans);
  return ans;
};
```
