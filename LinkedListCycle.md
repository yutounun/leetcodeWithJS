https://leetcode.com/problems/linked-list-cycle/description/

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */

/**
 * @param {ListNode} head
 * @return {boolean}
 */
// 1. Create two pointers. Slow pointer proceed 1 each loop but fast pointer proceed 2 on each loop.
// 2. Matching those two pointer means the array is linkedList and returns true.
var hasCycle = function (head) {
  let slow = head;
  let fast = head;

  // If there isn't cycle in the linked list, fast pointer doesn't have beyond list.
  // As long as there is cycle in it, those two pointer will meet at some point.
  // In case head has only one list,
  // fast.next doesn't exist and while condition doesn't meet
  while (fast && fast.next && fast.next.next) {
    slow = slow.next;
    fast = fast.next.next;
    if (slow === fast) return true;
  }
  return false;
};
```
