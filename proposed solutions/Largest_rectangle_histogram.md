<h1>Largest rectangle in histogram</h1>
<h2>Current Approach:Brute force</h2>
<h2>passed 88 / 99 testcases </h2>
<h3 >Comments:
<span style="color:red">
"I think to optimize it we need to implement stack concept"
</span>
</h3>


<hr/>
<h3>Solution Code</h3>

```
class Solution {
    public int largestRectangleArea(int[] heights) {
      int[] arr=new int[heights.length+1];
      int[] prev_smaller=new int[heights.length+1];
      int[] next_smaller=new int[heights.length+1];
      for(int i=0;i<heights.length;i++){
          arr[i]=heights[i];
      }  
       for(int i=0;i<arr.length;i++){
         int flag=0;        
          for(int j=i-1;j>=0;j--){
            if(arr[j]<arr[i] && flag==0){
                prev_smaller[i]=j;
                flag=1;
            }
          }
            if(flag==0){
            prev_smaller[i]=-1;  
            }
      }


         for(int i=0;i<arr.length;i++){
         int flag=0;        
          for(int j=i+1;j<arr.length;j++){
            if(arr[j]<arr[i] && flag==0){
                next_smaller[i]=j;
                flag=1;
            }
          }
            if(flag==0){
            next_smaller[i]=-1;  
            }
      } 
      
        int area=0;
         for(int i=0;i<heights.length;i++){
          int width=next_smaller[i]-prev_smaller[i]-1;
            // System.out.println(width);
          int curr_area=heights[i]*width;
          if(curr_area>area){
            area=curr_area;
          }
                // System.out.println(curr_area);

      }
       return area;
    }
}


```

<hr />

