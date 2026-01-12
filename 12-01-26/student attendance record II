class Solution {
    public int checkRecord(int n) {
        int MOD = 1000000007;

        long P0 = 1, L1 = 0, L2 = 0;   // no A yet
        long AP0 = 0, AL1 = 0, AL2 = 0; // one A used

        for (int i = 1; i <= n; i++) {
            long newP0 = (P0 + L1 + L2) % MOD;        
            long newL1 = P0;                          
            long newL2 = L1;                          

            long newAP0 = (AP0 + AL1 + AL2 + P0 + L1 + L2) % MOD; 
            long newAL1 = AP0;
            long newAL2 = AL1;

            P0 = newP0;
            L1 = newL1;
            L2 = newL2;
            AP0 = newAP0;
            AL1 = newAL1;
            AL2 = newAL2;
        }

        long ans = (P0 + L1 + L2 + AP0 + AL1 + AL2) % MOD;
        return (int) ans;
    }
}
