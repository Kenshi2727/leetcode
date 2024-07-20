<h1>Container With Most Water Optimized Solution</h1>
<h2>Two Pointer Approach</h2>
<hr/>
<h3>Solution Code</h3>

```
class Solution {
    public int maxArea(int[] height) {
        int n=height.length;
        int max=0,temp=0,r=n-1,l=0;
            while(l!=r){
                if(height[l]<=height[r]){
                    temp=height[l]*(r-l);
                    l++;
                }
                else{
                    temp=height[r]*(r-l);
                    r--;
                }
                if(temp>max)
                    max=temp;
            }
            return max;
    }
}

```

<hr />
