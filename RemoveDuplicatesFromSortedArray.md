https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/

※ As explanation says, no need to return the array. All you have to do is to filter the nums you get as an arg.

You need to modify the nums array using splice method in case of JavaScript.
When you splice an element of nums, index will indicate current i + 2 in the next loop.
So you have to substract 1 from i.

2nd time

```javascript
var removeDuplicates = function (nums) {
  // Pointer is needed to avoid using index number which moves when you remove element.
  for (let i = 0; i < nums.length; i++) {
    if (nums[i] === nums[i + 1]) {
      nums.splice(i, 1);
      i--;
    }
  }
};
```
