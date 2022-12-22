1. Iterate digits array from the last digit to the digit
2. Increment last digit by 1
3. If the last digit will be less than 10, break the loop and return the changed digits array
4. If the last digit will be more than 10, the last digit will be 0 and go to the next loop untill find a digits having under 9.
5. If the digits are [9, 9, 9], you have to add 1 on top using unshift.

```javascript
var plusOne = function (digits) {
  for (var i = digits.length - 1; i >= 0; i--) {
    digits[i]++;
    if (digits[i] > 9) {
      digits[i] = 0;
    } else {
      return digits;
    }
  }
  digits.unshift(1);
  return digits;
};
```
