<h1>238. Product of Array Except Self</h1>
<h2>Prefix Sum Approach</h2>
<hr/>
<h3>Solution Code</h3>

```

class Solution {
    public int[] productExceptSelf(int[] nums) {
     int[] prefix=new int[nums.length];
     int[] suffix=new int[nums.length];
     int[] result=new int[nums.length];
     int pre=1;
     int suf=1; 
     for(int i=0;i<nums.length;i++){
         if(i==0){
            prefix[i]=1;
         }
         else{
        prefix[i]=pre*nums[i-1];
        pre=prefix[i];
        }   
     }

     for(int i=nums.length-1;i>=0;i--){
         if(i==nums.length-1){
            suffix[i]=1;
         }
         else{
        suffix[i]=suf*nums[i+1];
        suf=suffix[i];
        }   
     }
     
    for(int i=0;i<nums.length;i++){
         result[i]=prefix[i]*suffix[i];  
     }
    
     return result;
    }
}
```

<hr />