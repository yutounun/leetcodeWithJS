level: 7
1st time

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var arrayPairSum = function (nums) {
  // Sort the array in ascending order
  // The sorting function is defined such that if a is greater than b,
  // a positive number is returned, indicating to the sort function that a should come after b.
  nums.sort((a, b) => a - b);

  // Initialize a variable sum to keep track of the total sum of the smallest values of each pair
  var sum = 0;

  // Iterate over the sorted array, incrementing by 2 each time
  // This way, we're only dealing with the smallest values of each pair, since the array is sorted.
  for (var i = 0; i < nums.length; i += 2) {
    // Add the smallest value of the current pair to the sum
    sum += nums[i];
  }

  // Return the total sum of the smallest values of each pair
  return sum;
};
```

This function works by first sorting the array of numbers in ascending order. Then, it iterates over the sorted array, adding every other number starting from the first one (which are the smallest numbers of each pair, since the array is sorted) to a running sum. Finally, it returns this sum, which is the sum of the smallest numbers of each pair in the array.

まず、この問題は各ペアの最小値を求めるという制約があります。つまり、ペアの一方の値がどれだけ大きくても、それが合計に影響を与えるわけではありません。合計に影響を与えるのは常にペアの最小値です。

次に、最大の合計値を得るためには、できるだけ大きな値を最小値として選びたいと思うでしょう。これは配列を昇順にソートし、隣同士の数値をペアにすることで達成できます。

この理由は、ソートされた配列では隣同士の数値が最も近いため、それらをペアにすると最小値が可能な限り大きくなるからです。一方、大きな値と小さな値をペアにすると、小さな値が最小値となり、合計は小さくなります。

例えば、[1, 2, 3, 4]という配列があるとします。[1, 3]と[2, 4]をペアにすると、最小値の合計は 1 + 2 = 3 になります。しかし、[1, 2]と[3, 4]をペアにすると、最小値の合計は 1 + 3 = 4 になり、これが最大の合計値です。
