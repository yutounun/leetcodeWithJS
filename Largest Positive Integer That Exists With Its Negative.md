level:
1st time

My solution

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var findMaxK = function (nums) {
  // hashtable → O(2n)
  // loop over nums
  // In each loop, set the current number as a value on map and negative(positive number) as a key
  // check the largest num in nums array using for[i]
  // find if the current number is alreafy emerged
  const map = {};
  let ans = 0;
  for (const num of nums) {
    if (map[num]) {
      if (map[num] > 0 && ans < num) {
        ans = num;
      } else if (ans < Math.abs(num)) {
        ans = num;
      }
    }
    console.log("num :", ans, num);
    if (num < 0) {
      const reversedNum = Math.abs(num);
      map[num] = reversedNum;
    } else {
      const reversedNum = 0 - num;
      map[num] = reversedNum;
    }
    console.log("map :", map);
  }
  return ans;
};
```

Others

```javascript
const findMaxK = (nums) => {
  let numsSet = new Set(nums);
  let largestInteger = -1;

  for (let num of numsSet) {
    if (num > 0 && numsSet.has(-num)) {
      largestInteger = Math.max(largestInteger, num);
    }
  }

  // In case largestInteger hasn't updated
  return largestInteger === -1 ? -1 : largestInteger;
};
```
