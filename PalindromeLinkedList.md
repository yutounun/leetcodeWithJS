level: 4
2nd time

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @return {boolean}
 */
var isPalindrome = function (head) {
  const arr = [];
  while (head) {
    arr.push(head.val);
    head = head.next;
  }
  const reversedArr = [...arr];
  reversedArr.reverse();
  return arr === reversedArr;
  const isEqual = arr.every((value, index) => value === reversedArr[index]);
  return isEqual;
};
```
