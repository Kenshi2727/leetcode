<h1>Two Sum Optimized Solution</h1>
<h2>Hashmap Approach</h2>
<hr/>
<h3>Solution Code</h3>

<p>

class Solution {
    public int[] twoSum(int[] nums, int target) {
        int n=nums.length;
        //create a hashmap where key is nums[i] and value is i
        HashMap<Integer,Integer> map=new HashMap<>();
        for(int i=0;i<n;i++){
            map.put(nums[i],i);
        }

        //creating result array
        int[] result=new int[2];
        //if the current element is equal to the target
       for(int i=0;i<n;i++){
            if(nums[i]==target && map.containsKey(0)){
              result[0]=i;
              result[1]=map.get(0);
              return result;
            }
            else if(map.containsKey(target-nums[i])){
                //is the element non repeatble?
                if((map.get(target-nums[i]) > i )){
                    result[0]=i;
                    result[1]=map.get(target-nums[i]);
                    return result;
                }
            }
        }
        result[0]=-1;
        result[1]=-1;
        return result;
    }
}

</p>

<hr />