<h1>Minimum in Roated Array Optimized Solution</h1>
<h2>Binary Search Approach</h2>

<hr/>
<h3>Solution Code</h3>

```
class Solution {
    public int findMin(int[] nums) {
        int res=nums[0];
        int l=0,r=nums.length-1;
        while(l<=r){
            //for fully sorted portion
            if(nums[l]<nums[r]){
            res=Math.min(res,nums[l]);
            break;
            }

            int m=l-(l-r)/2;
            res=Math.min(res,nums[m]);

            //if in left sorted subarray
            if(nums[m]>=nums[l])
            l=m+1;
            else//if in right subarray
            r=m-1;
        }
        return res;
    }
}

```

<hr />
