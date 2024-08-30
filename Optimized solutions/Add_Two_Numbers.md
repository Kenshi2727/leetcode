<h1>Add Two Numbers Optimized Solution</h1>
<h2>Mathematical Approach</h2>

```
You must have done elementary mathematics in your school(I guess you have....), so just remember that and focus on the way how you add two numbers.
let's say you want to add 342 and 465,here's how you add them-

   1->carry
   3 4 2                       
 + 4 6 5                   
   -----
   8 0 7
   -----

In our case we have our number in reversed order in linked list which eventually makes it much more easier to find the sum.Here's how
it makes it easier:

Eg.-   3342 + 465
---


5->6->4->NULL
2->4->3->3

Since we have a null value which will create problem while adding values in nodes so instaed of null we will add a '0',

      1(carry)
5->6->4->0(assume a 0)
2->4->3->3
__________
7->0->8->3
__________

since the order is reversed hence we can transfer the carry to the next node which is actually the next decimal position and
that is exactly what we do while adding on paper, we forward the carry to the next decimal position. Imagine if the number wasn't
reversed, how hard it would be to forward the carry compared to this flowery situation.

There's one more test case you need to take care of:
 Let's say you want to add 7 and 8,

    1->(carry)
 7  
 8
 ____
 5->1 
 ____

That means we need to create a new node if a carry remains. So after completing the traversing the whole linked list, check if
any carry remains if so then in order to accomodate we need to create a new decimal position(orr in our case a new node in our
linked list).You can see that in the solution code I had done that after closing brackets of the while loop();
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
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
             ListNode result=new ListNode(0);//dummy node
             ListNode head=result;
             int carry=0;
             int val1,val2;
             while(l1!=null || l2!=null){
                if(l1!=null)
                    val1=l1.val;
                else
                    val1=0;

                if(l2!=null)
                    val2=l2.val;
                else
                    val2=0;
                int sum=val1+val2+carry;
                result.next=new ListNode(sum%10);
                result=result.next;
                carry=sum/10;


                if(l1!=null)
                l1=l1.next;

                if(l2!=null)
                l2=l2.next;

             }
             if(carry>0){
                    result.next=new ListNode(carry);
                }

                return head.next;
          }

    }

```

<hr />
