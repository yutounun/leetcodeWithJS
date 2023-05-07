level: 1
2nd time

The following answer is way better than my solution

```javascript
/**
 * @param {number} n
 * @return {string[]}
 */
var fizzBuzz = function (n) {
  const rtn = [];
  for (let i = 1; i <= n; i++) {
    let str = "";

    if (i % 3 === 0) {
      str += "Fizz";
    }
    if (i % 5 === 0) {
      str += "Buzz";
    }

    if (str === "") {
      str = i.toString();
    }

    rtn.push(str);
  }
  return rtn;
};
```
