https://leetcode.com/problems/longest-common-prefix/

The thing is with js we can sort strings and when we sort an array of different strings they will be sorted alphabetically, which means all we left to do is find the common part between the first and the last values in the sorted array. As simple as this:

```javascript
var longestCommonPrefix = function (strs) {
  // sort all strings in array by alphabet.
  // first string and last string will have uncommon alphabets the most.
  strs.sort();
  for (let i = 0; i < strs[0].length; i++) {
    // Compare el[i] of first string and last string
    // If those are not same, it returns el[0] ~ el[i]
    if (strs[0][i] !== strs[strs.length - 1][i]) {
      return strs[0].substr(0, i);
    }
  }
  return strs[0];
};
```
