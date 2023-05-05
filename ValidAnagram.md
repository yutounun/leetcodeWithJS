level: 6
2nd time

```javascript
function isAnagram(s, t) {
  if (s.length !== t.length) return false;

  const sMap = {};
  for (const char of s) {
    if (sMap[char] > 0) {
      sMap[char]++;
    } else {
      sMap[char] = 1;
    }
  }
  const tMap = {};
  for (const char of t) {
    if (tMap[char] > 0) {
      tMap[char]++;
    } else {
      tMap[char] = 1;
    }
  }
  return areObjectsEqual(sMap, tMap);
}

function areObjectsEqual(obj1, obj2) {
  const keys1 = Object.keys(obj1);
  const keys2 = Object.keys(obj2);

  if (keys1.length !== keys2.length) return false;

  for (const key of keys1) {
    if (obj1[key] !== obj2[key]) return false;
  }

  return true;
}
```
