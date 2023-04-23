https://leetcode.com/problems/valid-palindrome/description/

1. First attempt → Failure
2. second attempt → Failure

```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
var isPalindrome = function (str) {
  // Change all characters into lower case.
  const lowStr = str.toLowerCase();

  filteredLowStr = lowStr.replaceAll(" ", "");
  filteredLowStr = filteredLowStr.replaceAll(",", "");
  filteredLowStr = filteredLowStr.replaceAll(":", "");
  filteredLowStr = filteredLowStr.replaceAll(".", "");

  const reversedStr = filteredLowStr.split("").reverse().join("");
  console.log("filteredLowStr :", filteredLowStr);
  console.log("reversedStr :", reversedStr);
  return reversedStr === filteredLowStr;
};
```

2. Second attempt → Best Solution

```javascript
var isPalindrome = function (str) {
  let newStr = "";
  for (let i = 0; i < str.length; i++) {
    lowStr = str[i].toLowerCase();
    char = "abcdefghijklnmopqrstuvqxyz1234567890";

    // Check if each word is included in char and is char or number.
    if (char.includes(lowStr)) {
      newStr += lowStr;
    }
  }
  // Reverse string
  const reversedS = newStr.split("").reverse().join("");
  return reversedS === newStr;
};
```

3. Third attempt

```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
var isPalindrome = function (str) {
  let newStr = "";
  for (let i = 0; i < str.length; i++) {
    lowStr = str[i].toLowerCase();
    char = "abcdefghijklnmopqrstuvqxyz1234567890";

    if (char.includes(lowStr)) {
      newStr += lowStr;
    }
  }

  let left = 0;
  let right = newStr.length - 1;

  while (left < right) {
    console.log("newStr[left], newStr[right] :", newStr[left], newStr[right]);
    if (newStr[left] !== newStr[right]) {
      return false;
    }
    right--;
    left++;
  }
  return true;
};
```

4th

```javascript
var isPalindrome = function (str) {
  let word = "";
  chars = "abcdefghijklnmopqrstuvqxyz1234567890";
  for (let i = 0; i < str.length; i++) {
    // convert string to small letters
    lowStr = str[i].toLowerCase();
    // remove symbols and spaces
    if (chars.includes(lowStr)) {
      word += lowStr;
    }
  }
  // reverse new value
  const reversedS = word.split("").reverse().join("");
  // compate two values
  return reversedS === word;
};
```
