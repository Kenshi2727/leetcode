
<p>
class Solution {<br />
    public int maximumEnergy(int[] energy, int k) {<br />
        int i,j,sum,res = Integer.MIN_VALUE;<br />
        int len = energy.length;<br />
        for(i=0;i<len;i++){<br />
            sum=0;<br />
            for(j=i;j<len;j+=k){<br />
                sum += energy[j];<br />
            }<br />
            if(sum > res)<br />
            {<br />
                res = sum;<br />
            }<br />
        }<br />
        return res;<br />
    }<br />
}<br />
</p>


<hr/>

<h1>AUTHOR-AYUSH GUPTA</h1>
<h2>Author's Github Profile</h2>
<a href="https://github.com/Ayush18012003"><img src="../images/Screenshot 2024-05-12 142206.png"/></a>

