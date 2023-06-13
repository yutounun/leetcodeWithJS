level: 8
1st time

My solution
time Beats %
space Beats %

```javascript

```

Others

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
 * @return {void} Do not return anything, modify head in-place instead.
 */
// 1234567
// slow will be 4 and fast will be 7
// the direction from the nodes in second half will be reversed as following
// 1→2→3 4←5←6←7
// 1, 7, 2, 6, 3, 5, 4
var reorderList = function (head) {
  // find the mid node
  let fast = head,
    slow = head;
  while (fast && fast.next) {
    fast = fast.next.next;
    slow = slow.next;
  }

  // reverse the way of the second half nodes
  let current = slow,
    prev = null;
  while (current) {
    let tmpNext = current.next;
    current.next = prev;
    prev = current;
    current = tmpNext;
  }

  // Merge 1st half and 2nd half
  let first = head,
    second = prev;
  while (second.next) {
    let tmpNext = first.next;
    first.next = second;
    first = tmpNext;

    tmpNext = second.next;
    second.next = first;
    second = tmpNext;
  }
  return head;
};
```
