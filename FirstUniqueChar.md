level: 4
2nd time

```javascript
/**
 * @param {string} s
 * @return {number}
 */
var firstUniqChar = function (s) {
  const charFrequency = {};

  // Iterate over the string to build the frequency map
  for (const char of s) {
    if (!charFrequency[char]) {
      charFrequency[char] = 1;
    } else {
      charFrequency[char]++;
    }
  }

  // Iterate over the string again to find the first unique character
  for (let i = 0; i < s.length; i++) {
    if (charFrequency[s[i]] === 1) {
      return i;
    }
  }

  return -1;
};
```
