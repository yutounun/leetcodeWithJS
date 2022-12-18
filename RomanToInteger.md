```javascript
const romanToInt = function (s) {
  set = {
    I: 1,
    V: 5,
    X: 10,
    L: 50,
    C: 100,
    D: 500,
    M: 1000,
  };

  s = s.replace("IV", "IIII").replace("IX", "VIIII");
  s = s.replace("CD", "CCCC").replace("CM", "DCCCC");
  s = s.replace("XL", "XXXX").replace("XC", "LXXXX");

  console.log(s);

  const str = s.split("");
  let rtn = 0;
  str.forEach((s) => {
    rtn += set[s];
  });
  return rtn;
};
```
