class Solution {
    int[][] memo;
    int[] p;
    int n;

    public int stoneGameII(int[] piles) {
        n = piles.length;
        memo = new int[n+1][n+1];
        p = new int[n+1];

        for (int i = 0; i < n; i++) {
            p[i+1] = p[i] + piles[i];
        }

        return f(0, 1);
    }

    int f(int i, int m) {
        if (i + 2 * m >= n) {
            return p[n] - p[i];
        } else if (memo[i][m] > 0) {
            return memo[i][m];
        }
        
        // other player's val. We want to make sure
        // other player gets the worst possible value.
        // We are going to subtract this value from remaining
        // total sum of stone[i], stone[i+1] .. stone[n-1]
        // so that we get the best result, from whatever is left

        int val = Integer.MAX_VALUE;
        for (int j = 1; j <= 2 * m; j++) {
            val = Math.min(val, f(i+j, Math.max(j, m))); 
        }

        return memo[i][m] = p[n] - p[i] - val;
    }
}
