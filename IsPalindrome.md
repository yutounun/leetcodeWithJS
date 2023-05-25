level: 2
3rd time

My solution
time Beats %
space Beats %

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
  let p1 = 0;
  let p2 = word.length - 1;
  while (p1 <= p2) {
    if (word[p1] !== word[p2]) {
      return false;
    }
    p1++;
    p2--;
  }
  return true;
};
```

Others

```javascript
var isPalindrome = function (str) {
  const chars = "abcdefghijklmnopqrstuvwxyz1234567890";
  let p1 = 0;
  let p2 = str.length - 1;

  while (p1 <= p2) {
    let char1 = str[p1].toLowerCase();
    let char2 = str[p2].toLowerCase();

    if (!chars.includes(char1)) {
      p1++;
      continue;
    }
    if (!chars.includes(char2)) {
      p2--;
      continue;
    }
    if (char1 !== char2) {
      return false;
    }
    p1++;
    p2--;
  }
  return true;
};
```
