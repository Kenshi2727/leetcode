# Minnimum in Roatated Array Problem Solution

## Approach- Modulo Addition

### Time complexity-O(n)

### status-accepted

```
class Solution {
    public int findMin(int[] nums) {
      int i=0;
      int j=i;
      if(nums.length==1)
      return nums[0];
      while(nums[j]<=nums[i]){
        j=i;
        i=(i+1)%nums.length;
      }
      return nums[i];
    }
}

```
