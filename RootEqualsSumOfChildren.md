first time
level: 3

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
 * @param {number} low
 * @param {number} high
 * @return {number}
 */
var rangeSumBST = function (root, low, high) {
  // 1. push all node value into an array using a recursive function
  // 2. sort an array
  // 3. iterate the array once and add on "ans" variable,
  // if the current value is between high and low
  // another way:
  // 1. Traverse all node value of the provided tree using a recursive function
  // 2. only when the value of node is between low and hight, add a number on the sum variable
  let sum = 0;
  function traverseTree(node) {
    if (!node) return;

    // if node exist
    const val = node.val;
    if (val <= high && low <= val) {
      sum += val;
    }
    traverseTree(node.left);
    traverseTree(node.right);
  }
  traverseTree(root);
  return sum;
};
```
