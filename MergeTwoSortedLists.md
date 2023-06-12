https://leetcode.com/problems/merge-two-sorted-lists/

3nd time
Level: 5

1. Create a newList ListNode.
2. Copy the ListNode you created to save the head of newListList.
3. Iterate two of args and compare each element to find smaller number.
4. Assign smaller number to the next value of newList.
5. First node of rtnList is null so return the next value of rtnList.

```javascript
var mergeTwoLists = function (l1, l2) {
  let rtnList = new ListNode(null, null);
  let newList = rtnList;

  while (l1 && l2) {
    if (l1.val > l2.val) {
      newList.next = l2;
      l2 = l2.next;
    } else {
      newList.next = l1;
      l1 = l1.next;
    }
    newList = newList.next;
  }
  // assigns the remaining nodes from either l1 or l2 (whichever is not null) to newList.next.
  // After while loop, one of these node has no nodes
  newList.next = l1 || l2;
  return rtnList.next;
};
```
