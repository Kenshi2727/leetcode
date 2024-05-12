<body>
class Solution {
    int cal_energy(int k, int[] energy) {
        int t, result = -1000, i, j;
        for (i = 0; i < energy.length; i++) {
            t = 0;
            for (j = i; j < energy.length; j += k) {
                t += energy[j];
            }
            if (t > result) 
                result = t;
        }
        return result;
    }

    public int maximumEnergy(int[] energy, int k) {
        return cal_energy(k, energy);
    }
}
</body>

<hr/>

<h1>AUTHOR-SYED ALI ASAD</h1>
<h2>Author's Github Profile</h2>
<a href="https://github.com/syedaliasad649"><img src="images/Screenshot 2024-05-12 142206.png"/></a>

