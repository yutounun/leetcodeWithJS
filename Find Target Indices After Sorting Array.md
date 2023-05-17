level:
1st time

My solution

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var targetIndices = function (nums, target) {
  // look over all elements and push matched number with target to ans array
  const ans = [];
  nums.sort((a, b) => {
    return a - b;
  });
  for (let i = 0; i < nums.length; i++) {
    if (target === nums[i]) {
      ans.push(i);
    }
  }
  return ans;
};
```

Others

```javascript
const targetIndices = function (nums, target) {
  nums.sort((a, b) => a - b);
  let index = binarySearch(nums, target);

  if (index === -1) {
    return [];
  }

  let res = [index];
  let l_index = index - 1;
  let r_index = index + 1;

  for (let i = l_index; i >= 0; i--) {
    if (nums[i] === target) {
      res.unshift(i);
    } else {
      break;
    }
  }

  for (let i = r_index; i <= nums.length; i++) {
    if (nums[i] === target) {
      res.push(i);
    } else {
      return res;
    }
  }
};

function binarySearch(arr, target) {
  let l = 0;
  let r = arr.length - 1;

  while (l <= r) {
    let middle = Math.floor((l + r) / 2);

    if (arr[middle] === target) {
      return middle;
    } else if (target < arr[middle]) {
      r = middle - 1;
    } else {
      l = middle + 1;
    }
  }

  return -1;
}
```
