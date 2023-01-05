This runs out of time :( → Failure!!

```javascript
// 1. Create an empty stack
// 2. Push elements in the nums array into stack array
// 3. If current element in a loop is already in stack, remove both from stack and nums.
// 4. At last, return a left element in stack

var singleNumber = function (nums) {
  const stack = [];
  for (let i = 0; i < nums.length; i++) {
    if (stack.includes(nums[i])) {
      const index = stack.indexOf(nums[i]);
      // This cannot be "if(index)"
      // cuz when index is 0, index is false and doesn't pass condition
      if (index !== -1) {
        stack.splice(index, 1);
      }
      nums.splice(i, 1);
      // Substact i - 1 since the number of elements decrease
      i--;
    } else {
      stack.push(nums[i]);
    }
  }
  return stack[0];
};
```

Success using hashmap

```javascript
function singleNumber(nums) {
  const map = {};
  for (let num of nums) {
    if (map[num] == null) map[num] = 0;
    // Everytime same number appears, add 1 on the number key's value
    map[num]++;
  }
  //  Each values in map means the count of appearance
  console.log("map :", map); // { '1': 1, '2': 2 }

  // Iterate only keys by using let ... in
  for (let num in map) {
    if (map[num] === 1) return Number(num);
  }
}
```
