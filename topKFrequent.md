level: 6
1st time

My solution
time Beats %
space Beats %

```javascript

```

Others

```javascript
/**
 * @param {number[]} nums
 * @param {number} k
 * @return {number[]}
 */
var topKFrequent = function (nums, k) {
  // hashmap
  // count frequency of all numbers. appearing on a given num
  // loop over the map to find the 2 most frequent value
  const map = {};
  for (const num of nums) {
    if (!map[num]) {
      map[num] = 1;
    } else {
      map[num]++;
    }
  }
  console.log(
    " :",
    Object.entries(map)
      .sort((a, b) => b[1] - a[1])
      .slice(0, k)
      .map((entry) => entry[0])
  );
  return Object.entries(map)
    .sort((a, b) => b[1] - a[1])
    .slice(0, k)
    .map((entry) => entry[0]);
};
```
