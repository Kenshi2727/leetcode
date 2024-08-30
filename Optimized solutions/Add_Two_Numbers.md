<h1>Add Two Numbers Optimized Solution</h1>
<h2>Mathematical Approach</h2>
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
