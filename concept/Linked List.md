# Linked List

__876. Middle of the Linked List__

Given the `head` of a singly linked list, return the middle node of the linked list.
If there are two middle nodes, return the second middle node.

__Approach__

Each time, `slow` go 1 step while `fast` go 2 steps.
When `fast` arrives at the end, `slow` will arrive right in the middle.

__Java__

```java
public ListNode middleNode(ListNode head) {
        ListNode slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        return slow;
}
```    
__JavaScript__
```javascript
/*
initial state
f
1 -> 2 -> 3 -> 4 -> 5
s

1st loop
		  f
1 -> 2 -> 3 -> 4 -> 5
     s
	 
2nd loop
		            f
1 -> 2 -> 3 -> 4 -> 5
          s

when f reach end of the linked list, s will be at the middle.

f = fast pointer
s = slow pointer
*/
var middleNode = function(head) {
    let fast = slow = head;
    while (fast && fast.next) {
        fast = fast.next.next;
        slow = slow.next;
    }
    return slow;
};
```
__21. Merge Two Sorted Lists__

You are given the heads of two sorted linked lists list1 and list2.
Merge the two lists in a one sorted list. The list should be made by splicing together the nodes of the first two lists.
Return the head of the merged linked list.
