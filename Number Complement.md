level: 6
1st time

My solution
time Beats %
space Beats %

```javascript
var findComplement = function (num) {
  // Convert the number to binary
  var binary = num.toString(2);

  // Flip the bits
  var flipped = "";
  for (var i = 0; i < binary.length; i++) {
    flipped += binary[i] === "0" ? "1" : "0";
    console.log("flipped :", flipped, binary[i]);
  }

  // Convert back to decimal and return
  return parseInt(flipped, 2);
};
```

Others

```javascript

```
