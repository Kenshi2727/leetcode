<h1>Merge Interval Optimized Solution</h1>
<h2>LinkedList Approach</h2>
<hr/>
<h3>Solution Code</h3>

```
class Solution {
    public int[][] merge(int[][] intervals) {
        //sorting intervals in ascending order of start value
        //[0] - start
        //[1] - end
        // O(nlogn) time complexity
        // O(n) space complexity assuming merge sort to be used for sorting
        Arrays.sort(intervals,(a,b)->Integer.compare(a[0],b[0]));

        //iterate over all the intervals and check for the overlapping intervals
        LinkedList<int[]> merged=new LinkedList<>();
        for(int[] interval:intervals){
            //non overlapping
            if(merged.isEmpty() || merged.getLast()[1] < interval[0])
              merged.add(interval);
            else{
                //overlapping
                //take max(lastEnd,End)
                merged.getLast()[1]=Math.max(merged.getLast()[1],interval[1]);
            }
        }
        return merged.toArray(new int[merged.size()][]);
    }
}

```

<hr />
