https://leetcode.com/problems/climbing-stairs/submissions/
[ref](https://dev.to/urfan/leetcode-climbing-stairs-with-javascript-1dme)

if n = 1, return 1

if n=2, return 2

if n=3, return 3

if n=4, return 5

1,1,1,1

1,1,2

2,2

2,1,1

1,2,1

if 5, return 8

1.1.1.1.1

1,1,1,2

1,2,1,1

1,1,2,1

2,1,1,1,

2,1,2

2,2,1

1,2,2

From this rule, we can say that this is fibonacci array.
So the solution will be

```javascript
var climbStairs = function (n) {
  if (n < 2) return 1;

  let first = 1;
  let second = 2;

  for (let i = 3; i <= n; i++) {
    let third = first + second;
    first = second;
    second = third;
  }
  return second;
};
```
