<h1>Sliding Window Optimized Solution</h1>
<h2>Deque Approach</h2>
<hr/>
<h3>Solution Code</h3>

```
class Solution {
    public int[] maxSlidingWindow(int[] nums, int k) {
      Deque<Integer> q=new ArrayDeque<>();
      int n=nums.length;
      int result[]=new int[n-k+1];
      int index=0;
      int i;
      for(i=0;i<k;i++){  //0 1 2
       while((!q.isEmpty()) && nums[i]>=nums[q.peekLast()]){
        q.removeLast();
       }

       //add new element at the rear of queue
       q.addLast(i);
      } 
    
     //code for the rest of elements
      for(;i<n;i++){

      //adding max elemts into result array
      result[index]=nums[q.peek()];
      index++;

       //checking front if it is out of the window
        while((!q.isEmpty()) && q.peek() <= i-k){
           q.removeFirst();
        } 
        
        while((!q.isEmpty()) && nums[i]>=nums[q.peekLast()]){
         q.removeLast();
        }

       //add new element at the rear of queue
       q.addLast(i);
      } 


      //adding maximum element of the last window as loop will stop
      result[index]=nums[q.peek()];
      return result;
    }
}

```

<hr />