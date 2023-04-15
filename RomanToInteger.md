https://leetcode.com/problems/roman-to-integer/
2nd time

Easiest and understandable answer.
If the current numeral is less than the next one, subtract the current one from value.
Instead, in the next step, you can add the big number just normally.

```javascript
symbols = {
  I: 1,
  V: 5,
  X: 10,
  L: 50,
  C: 100,
  D: 500,
  M: 1000,
};

var romanToInt = function (s) {
  value = 0;
  for (let i = 0; i < s.length; i += 1) {
    const current = s[i];
    const next = s[i + 1];
    symbols[current] < symbols[next]
      ? (value -= symbols[current])
      : (value += symbols[current]);
  }
  return value;
};
```
