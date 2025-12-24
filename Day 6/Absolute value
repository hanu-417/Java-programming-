class Solution {
    public int maxAbsValExpr(int[] arr1, int[] arr2) {
        int n = arr1.length;
        int maxVal = Integer.MIN_VALUE;
        int[][] signs = {
            {1, 1, 1},
            {1, 1, -1},
            {1, -1, 1},
            {1, -1, -1},
            {-1, 1, 1},
            {-1, 1, -1},
            {-1, -1, 1},
            {-1, -1, -1}
        };

        for (int[] sign : signs) {
            int maxExpr = Integer.MIN_VALUE;
            int minExpr = Integer.MAX_VALUE;

            for (int i = 0; i < n; i++) {
                int val = sign[0] * arr1[i] + sign[1] * arr2[i] + sign[2] * i;
                maxExpr = Math.max(maxExpr, val);
                minExpr = Math.min(minExpr, val);
            }

            maxVal = Math.max(maxVal, maxExpr - minExpr);
        }

        return maxVal;
    }
}
