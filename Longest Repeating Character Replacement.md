level:
1st time

My solution
time Beats %
space Beats %

```javascript

```

Others

```javascript
// Input: s = "AABABBA", k = 1
// Output: 4
// Explanation: Replace the one 'A' in the middle with 'B' and form "AABBBBA".
// The substring "BBBB" has the longest repeating letters, which is 4.
// There may exists other ways to achive this answer too.

const characterReplacement = (s, k) => {
  let left = 0;
  let right = 0;
  let max = 0;
  const count = {};

  while (right < s.length) {
    const char = s[right];
    // Use hashmap to find the frequency of each char
    count[char] = count[char] ? count[char] + 1 : 1;

    // update max
    if (count[char] > max) max = count[char];

    // the following line is critical
    // right - left + 1 meaning window size
    // when window size - occurency of the most freq char is more than k, move left pointer forward.
    // window内にK個までの異端児なら変更できるが、それを超えるとキャパオーバーだから左を消し、カウントも減らす
    if (right - left + 1 - max > k) {
      count[s[left]]--;
      left++;
    }

    right++;
  }

  // right is added by 1 on the above line, so no need to do +1
  return right - left;
};
```
