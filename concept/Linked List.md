# Linked List


__Must-Do LinkedList Problems on Leetcode__
- Add Two Numbers
- Remove Nth Node From End of List
- Merge Two Sorted Lists
- Merge K Sorted Lists
- Reorder List
- Swap Nodes In Pairs
- Partition Lists
- Reverse a Linked List II
- Convert Sorted List to Binary Search Tree
- Copy List with Random Pointer
- Linked List Cycle II
- Odd-Even Linked List
- Next Greater Node In Linked List

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
```java
class Solution {
    public ListNode mergeTwoLists(ListNode A, ListNode B) {
        if(A == null) return B;
	    if(B == null) return A;
        ListNode temp = A.val < B.val ? A: B;
        ListNode head=temp;
        if(A.val<B.val) 
            A=A.next;
        else 
            B=B.next;

        while(A!=null && B!=null){
            if(A.val<B.val){
                temp.next=A;
                A=A.next;
            }
            else{
                temp.next=B;
                B=B.next;
            }
            temp=temp.next;
        }
        if(A==null){
            temp.next=B;
        }
        else {
            temp.next=A;
        }
        return head;
    }
}
```
__LRU Cache__
```java
class ListNode{
    int data;
    int key;
    ListNode next;
    ListNode prev;
    ListNode(int data,int key){
        this.data=data;
        this.key=key;
    }
}
public class Solution {
    int capacity;
    ListNode head=new ListNode(-1,-1);
    ListNode tail=new ListNode(-1,-1); // anchor nodes to prevent null pointer
    HashMap<Integer,ListNode> map;

    public Solution(int capacity) {
        head.next=tail;
        tail.prev=head;  
        this.capacity=capacity;
        map=new HashMap<Integer,ListNode>();
    }
   
    public int get(int key) {
        if(map.containsKey(key)){
          int toReturn=map.get(key).data;
          ListNode og=map.get(key);
          ListNode t1=og.prev;
          ListNode t2=og.next;
          t1.next=t2;
          t2.prev=t1;
          ListNode t3=tail.prev;
          og.next=tail;
          og.prev=tail.prev;
          tail.prev=og;
          t3.next=og;
          return toReturn;  
        }
        else
            return -1;
    }
   
    public void set(int key, int value) {
        if(map.containsKey(key)){
            ListNode t1=map.get(key);
            ListNode t2=t1.prev;
            ListNode t3=t1.next;
            t2.next=t3;
            t3.prev=t2;
            t1=null;
            map.remove(key);
        }
        else if(map.size()==capacity){
            map.remove(head.next.key);  //reduce the mapsize
            //remove the first node
            ListNode t1=head.next;
            ListNode t2=t1.next;
            head.next=t2;
            t2.prev=head;
            t1=null;
        }
        //add a new node at the end of the cache
        ListNode newNode=new ListNode(value,key);
        ListNode temp1=tail.prev;
        temp1.next=newNode;
        newNode.next=tail;
        newNode.prev=temp1;
        tail.prev=newNode;
        map.put(key,newNode);
    }
}
```
