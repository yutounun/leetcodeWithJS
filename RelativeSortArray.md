level: 4
1st time

Better

```javascript
// Define the function with two input arrays
var relativeSortArray = function (arr1, arr2) {
  // Initialize an empty object to store the counts of each number in arr1
  let map = {};
  // Initialize an empty array to store the final result
  let res = [];

  // Loop over each number in arr1
  for (let num of arr1) {
    // If the number already exists in the map, increment its count
    if (map[num]) {
      map[num]++;
      // If the number does not exist in the map, add it to the map with a count of 1
    } else {
      map[num] = 1;
    }
  }

  // Loop over each number in arr2
  for (let num of arr2) {
    // While the number still has a count in the map, add it to the result array and decrement its count in the map
    while (map[num] > 0) {
      res.push(num);
      map[num]--;
    }
    // Once all instances of the number have been added to the result array, remove the number from the map
    delete map[num];
  }

  // Get the remaining numbers in the map (those that do not appear in arr2) and sort them in ascending order
  let remaining = Object.keys(map).sort((a, b) => a - b);

  // Loop over each remaining number
  for (let num of remaining) {
    // While the number still has a count in the map, add it to the result array and decrement its count in the map
    while (map[num] > 0) {
      res.push(Number(num)); // Number is used to convert the string key back to a number
      map[num]--;
    }
  }

  // Return the final sorted array
  return res;
};
```

Mine

```javascript
/**
 * @param {number[]} arr1
 * @param {number[]} arr2
 * @return {number[]}
 */
var relativeSortArray = function (arr1, arr2) {
  // brute force
  // sort arr1
  // create rtn array variable
  // add two pointers
  // if p2 = p1 push arr[p2] to rtn
  // if p2 === arr.length-1
  // return rtn

  const rtn = [];
  arr1.sort((a, b) => {
    return a - b;
  });
  let p1 = 0;
  let p2 = 0;

  while (p2 !== arr2.length) {
    if (p1 === arr1.length) {
      p2++;
      p1 = 0;
    }
    if (arr2[p2] === arr1[p1]) {
      rtn.push(arr1[p1]);
    }
    p1++;
    console.log("p1 :", p1);
  }
  for (const el of arr1) {
    if (!arr2.includes(el)) rtn.push(el);
  }
  return rtn;
};
```
