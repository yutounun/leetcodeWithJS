https://leetcode.com/problems/binary-tree-inorder-traversal/description/
Use callback functions to get a concise answer.

return an array with each values in the node

level: 8

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
