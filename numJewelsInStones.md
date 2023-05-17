level: 1
1st time

My solution

```javascript
/**
 * @param {string} jewels
 * @param {string} stones
 * @return {number}
 */
var numJewelsInStones = function (jewels, stones) {
  const map = [];
  let sum = 0;
  for (const stone of stones) {
    if (!map[stone]) {
      map[stone] = 1;
    } else {
      map[stone]++;
    }
  }

  const keys = Object.keys(map);
  for (const key of keys) {
    if (jewels.includes(key)) sum += map[key];
  }
  return sum;
};
```

Others

```javascript
/**
 * @param {string} jewels
 * @param {string} stones
 * @return {number}
 */
var numJewelsInStones = function (jewels, stones) {
  const map = [];
  let sum = 0;
  for (const stone of stones) {
    if (jewels.includes(stone)) sum++;
  }
  return sum;
};
```
