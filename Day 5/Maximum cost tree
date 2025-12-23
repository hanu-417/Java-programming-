class Solution {

    public static int[][] dp;
    
    public static int helper(int[] arr, HashMap<String, Integer> map, int left, int right) {
        if (left >= right) return 0; 

        if(dp[left][right] != -1){
            return dp[left][right];
        }
        int ans = Integer.MAX_VALUE;

        for (int i = left; i < right; i++) { 
            int leftMax = map.get(left + "#" + i);
            int rightMax = map.get((i + 1) + "#" + right);

            int temp = leftMax * rightMax + helper(arr, map, left, i) + 
            helper(arr, map, i + 1, right);
            ans = Math.min(ans, temp);
        }

        return dp[left][right] = ans;
    }

    public int mctFromLeafValues(int[] arr) {
        HashMap<String, Integer> map = new HashMap<>();
        int n = arr.length;

        
        for (int i = 0; i < n; i++) {
            for (int j = i; j < n; j++) { 
                if (i == j) {
                    
                    map.put(i + "#" + j, arr[i]);
                } else {
                    
                    int prevMax = map.get(i + "#" + (j - 1));
                    map.put(i + "#" + j, Math.max(prevMax, arr[j]));
                }
            }
        }
        dp = new int[n+1][n+1];
        for(int i = 0 ; i < n ; i++){
            Arrays.fill(dp[i],-1);
        }
        
        return helper(arr, map, 0, n - 1);
    }

    
}
