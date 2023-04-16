level: 8
first time

```javascript
/**
 * @param {string} haystack
 * @param {string} needle
 * @return {number}
 */
var strStr = function (haystack, needle) {
  if (haystack === needle || needle === "") return 0;
  if (haystack.length < needle.length) reuturn - 1;

  for (let i = 0; i < haystack.length; i++) {
    if (haystack[i] === needle[0]) {
      for (let j = 0; j < needle.length; j++) {
        if (haystack[i + j] !== needle[j]) {
          break;
        } else if (needle.length - 1 === j) {
          return i;
        }
      }
    }
  }
  return -1;
};
```
