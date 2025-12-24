class Solution {
    public int atMostNGivenDigitSet(String[] digits, int n) {
        char[] s = String.valueOf(n).toCharArray();
        int l = s.length;
        int numDigits = digits.length;
        
        // Example: If N is 100 (len 3), we count all 1-digit and 2-digit numbers.
        // We can pick any digit from the set freely.
        int totalCount = 0;
        for (int len = 1; len < l; len++) {
            totalCount += Math.pow(numDigits, len);
        }

        // memo[index][tight]
        int[][] dp = new int[l + 1][2];

        // Base case: If we successfully placed all digits, that's 1 valid number
        dp[l][0] = 1;
        dp[l][1] = 1;

        // Iterate backwards from last index
        for (int i = l - 1; i >= 0; i--) {
            for (int tight = 0; tight <= 1; tight++) {
                
                int limit = (tight == 1) ? (s[i] - '0') : 9;
                int count = 0;

                for (String dStr : digits) {
                    int val = Integer.parseInt(dStr);
                    
                    if (val < limit) {
                        count += dp[i + 1][0];
                    } else if (val == limit) {
                        count += dp[i + 1][tight]; 
                    } else {
                        break; 
                    }
                }
                dp[i][tight] = count;
            }
        }

        return totalCount + dp[0][1];
    }
}
