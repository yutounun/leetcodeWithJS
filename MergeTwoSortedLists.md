https://leetcode.com/problems/merge-two-sorted-lists/

1. Create a new ListNode.
2. Copy the ListNode you created.
3. Iterate two of args and compare each element to find smaller number.
4. Assign smaller number to the next value of newList.
5. First node of rtnList is null so return the next value of rtnList.

```javascript
var mergeTwoLists = function (list1, list2) {
  let rtnList = new ListNode(null, null);
  let newList = rtnList;

  while (list1 && list2) {
    if (list1.val > list2.val) {
      newList.next = list2;
      list2 = list2.next;
    } else {
      newList.next = list1;
      list1 = list1.next;
    }
    newList = newList.next;
  }
  newList.next = list1 || list2;
  return rtnList.next;
};
```
