```javascript
var isValid = function (s) {
  const stack = [];

  for (let i = 0; i < s.length; i++) {
    console.log("stack: ", stack);
    let c = s.charAt(i);
    console.log("c", c);
    switch (c) {
      case "(":
        stack.push(")");
        break;
      case "[":
        stack.push("]");
        break;
      case "{":
        stack.push("}");
        break;
      // else
      default:
        console.log("stack2 :", stack);
        if (c !== stack.pop()) {
          return false;
        }
    }
  }
  return stack.length === 0;
};
```
