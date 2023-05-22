level: 5
1st time

My solution
time Beats 58%
space Beats 41%

```javascript
var groupAnagrams = function (strs) {
  let obj = {};
  for (let str of strs) {
    let letters = str.split("").sort().join("");
    obj[letters] ? obj[letters].push(str) : (obj[letters] = [str]);
    console.log("obj :", obj);
  }
  return Object.values(obj);
};
```

Others

```javascript

```
