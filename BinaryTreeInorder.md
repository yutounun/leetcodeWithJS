https://leetcode.com/problems/binary-tree-inorder-traversal/description/
Use callback functions to get a concise answer.

```javascript
var inorderTraversal = function (root) {
  const res = [];
  function traverse(root) {
    if (!root) return;
    traverse(root.left);
    res.push(root.val);
    traverse(root.right);
  }
  traverse(root);
  return res;
};
```
