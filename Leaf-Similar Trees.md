level:
1st time

My solution
time Beats 96.14%
space Beats 85.76%

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
 * @param {TreeNode} root1
 * @param {TreeNode} root2
 * @return {boolean}
 */
var leafSimilar = function (root1, root2) {
  // Depth first search
  // using recursion
  // visit each edge leaf and push the value to the ans array
  // compare both arrays
  const arr1 = [];
  const arr2 = [];
  function recursive1(node) {
    if (!node) return true;
    if (!node.left && !node.right) {
      arr1.push(node.val);
      // console.log(' :', arr1)
    }
    recursive1(node.left);
    recursive1(node.right);
  }
  function recursive2(node) {
    if (!node) return true;
    if (!node.left && !node.right) {
      arr2.push(node.val);
      // console.log(' :', arr2)
    }
    recursive2(node.left);
    recursive2(node.right);
  }
  recursive1(root1);
  recursive2(root2);
  if (arr2.length !== arr1.length) return false;
  // O(n)
  for (let i = 0; i < arr1.length; i++) {
    if (arr1[i] !== arr2[i]) return false;
  }
  return true;
};
```

Others

```javascript

```
