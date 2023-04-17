# Overview

This page is where I write about what I learnt thorough LeetCode.

## HashMap

ex: TwoSums

```javascript
const myMap = new Map([
  ["key1", "value1"],
  ["key2", "value2"],
  ["key3", "value3"],
]);

// Accessing values
console.log(myMap.get("key1")); // 'value1'

// Adding new key-value pairs
myMap.set("key4", "value4");

// Removing a key-value pair
myMap.delete("key1");

// Checking if a key exists
console.log(myMap.has("key1")); // false

// Iterating over key-value pairs
myMap.forEach((value, key) => {
  console.log(key, value);
});
```

Looks similar to Object in Javascript but has way more functions to operate data in HashMap.

## Iterate string

You don't have to split string into each characters to iterate that.

```javascript
const string = "hello";
string.forEach((el) => {
  console.log(el); // "h"....
});
```

## Substr()

Get specified characters from strings.

```javascript
const example = "example";
const rtn = example.substr(1, 3);
console.log(rtn); // "xam"
```

## Big O

- Big O of N
- Big O of N squared
- Big O of M times N

## IndexOf

The following code returns the first index of haystack starting to include needle value

```javascript
const haystack = "hello";
const need = "he";
return haystack.indexOf(needle); // 0
```

## Dynamic Programing

This saves data to avoid calculating multiple times.
The fibonacci sequence (Emerged on Climbing Stairs problem) is the representative example of using this.

## Sort numbers including negative number

```javascript
nums1.sort((a, b) => {
  return a - b;
});
```

## Tree Structure

Use recursive function
