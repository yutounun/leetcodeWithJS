1st time
lelvel: 5

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var majorityElement = function (nums) {
  // Initialize a HashMap to store the frequency of each element
  // Loop through the elements in the 'nums' array
  // If an element is already present in the HashMap, increment its count by 1
  // If the element is not present, add it to the HashMap with a count of 1
  // If the count of any element exceeds half the length of the array, return that element
  const ans = {};
  for (const num of nums) {
    if (ans[num] > 0) {
      ans[num]++;
    } else {
      ans[num] = 1;
    }
    if (ans[num] > nums.length / 2) return num;
  }
};
```
