https://leetcode.com/problems/valid-parentheses/

second time

```javascript
var isValid = function (s) {
  // ()→true
  // (]→false
  // ([])→false
  // ()[]→true

  const stack = [];

  // iterate s
  for (const i of s) {
    switch (i) {
      case "(":
        stack.push(")");
        break;
      case "{":
        stack.push("}");
        break;
      case "[":
        stack.push("]");
        break;
      default:
        if (stack.pop() !== i) {
          return false;
        }
    }
  }
  return stack.length === 0;
};
```
