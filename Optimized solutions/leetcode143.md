<h1>Reorder List Optimized Solution</h1>
<h2>Linked List splitting Approach</h2>

```
If we see the problem carefully you will observe that we are taking nodes from the start and from the end alternatively one
by one and thereby forming the required arrangement.
Eg.-
----
1 -> 2 -> 3 -> 4
first take 1
1(start)
then take 4(end)
1->4
now take 2(new start)
1->4->2
then take 3(new end)
1->4->2->3

Final Output-
1 -> 4 -> 2 -> 3

It is  also applicable to odd length linked list.
1 -> 2 -> 3 -> 4-> 5
first take 1
1(start)
then take 5(end)
1->5
now take 2
1->5->2
then take 4
1->5->2->4
now take 3
1->5->2->4->3

Final Output-
1 -> 5 -> 2 -> 4 -> 3

Observe one thing very carefully. We are alternatively taking form start and end that means we can divide the linkedlist
into parts and reverse the second part  of linked list and then select the nodes from first part and second part alternatively.

We will use the concept of slow and fast pointers to reach the middle of linkedlist. Do not worry about odd length linkedlist.
In this case second part of linked list will be shorter than the first part but it will not affect the logic and we will still
get the desired output.You can dry run yourself after analyzing the code.


Step 1 - Reach the middle of linked list using slow and fast pointers
------
first half |  second half
           | 
1 -> 2 -> 3| -> 4-> 5 -> null
          ||              |
         slow           fast
           |
           |

Step 2- Reverse the links in the second half
------

first half |  second half
           | 
1 -> 2 -> 3| <-4 <- 5 
           |         
           |     
           |

Step-3 Split the linked list into two parts
------
1 -> 2 -> 3 -> null
      and 
5 -> 4 -> null

step-4 Merge them by choosing the nodes alternatively from the respective spliited linked lists
------
Final Output-
1 -> 5 -> 2 -> 4 -> 3

```
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
