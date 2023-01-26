# Linked List

__876. Middle of the Linked List__

Given the `head` of a singly linked list, return the middle node of the linked list.
If there are two middle nodes, return the second middle node.

_solution_
==Each time, `slow` go 1 step while `fast` go 2 steps.==
When `fast` arrives at the end, `slow` will arrive right in the middle.

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
