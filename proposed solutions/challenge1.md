
<p>
class Solution {                            <br/>
    int cal_energy(int k, int[] energy) {       <br/>
        int t, result = -1000, i, j;<br/>
        for (i = 0; i < energy.length; i++) {<br/>
            t = 0;<br/>
            for (j = i; j < energy.length; j += k) {<br/>
                t += energy[j];<br/><br/>
            }<br/>
            if (t > result) <br/>
                result = t;<br/>
        }<br/>
        return result;<br/>
    }<br/>

    public int maximumEnergy(int[] energy, int k) {<br/>
        return cal_energy(k, energy);<br/>
    }<br/>
}<br/>
</p>


<hr/>

<h1>AUTHOR-SYED ALI ASAD</h1>
<h2>Author's Github Profile</h2>
<a href="https://github.com/syedaliasad649"><img src="images/Screenshot 2024-05-12 142206.png"/></a>

