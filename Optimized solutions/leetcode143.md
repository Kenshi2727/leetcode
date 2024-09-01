<h1>Reorder List Optimized Solution</h1>
<h2>Linked List splitting Approach</h2>
<hr/>
<h3>Solution Code</h3>

```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public void reorderList(ListNode head) {
        ListNode slow=head;
        ListNode fast=head.next;

        //to reach the middle of linked list
        while(fast!=null && fast.next!=null){
            slow=slow.next;
            fast=fast.next.next;
        }

        ListNode first=head;//beginning of first half
        ListNode second=slow.next;//beginning of second half
        ListNode prev=null;
        //splitted list into two parts
        slow.next=null;

        //reversing second half
        while(second!=null){
            ListNode temp=second.next;
            second.next=prev;
            prev=second;
            second=temp;
        }
        second=prev;


        //merging the two splitted list
        while(second!=null){//we know that second half will either be less than or equal to first half
            ListNode temp1=first.next;
            ListNode temp2=second.next;
            first.next=second;
            second.next=temp1;
            first=temp1;
            second=temp2;
        }
    }
}
```

<hr />
