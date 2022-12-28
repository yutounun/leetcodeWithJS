https://leetcode.com/problems/symmetric-tree/description/

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
var isSymmetric = function (root) {
  // In case, all the child nodes on the left and right are symmetric around its center
  return checkTree(root.right, root.left);
};
function checkTree(rightNode, leftNode) {
  if (!rightNode && !leftNode) return true;
  // In case of one of two nodes is null
  if (!rightNode || !leftNode) return false;

  // If value of rightNode and leftNode are equal, return False on that recursive.
  if (rightNode.val !== leftNode.val) return false;

  // In case of not symmetric
  if (!checkTree(rightNode.right, leftNode.left)) return false;
  if (!checkTree(leftNode.right, rightNode.left)) return false;

  return true;
}
```
