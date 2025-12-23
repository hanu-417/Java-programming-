class Solution {
    public int longestWPI(int[] hours) {
        int n = hours.length;
        int[] score = new int[n];

        for(int i = 0; i < n; i++) {
            score[i] = hours[i] > 8 ? 1 : -1;
        }

        int[] prefixSum = new int[n+1];
        for(int i = 0; i < n; i++) {
            prefixSum[i+1] = prefixSum[i] + score[i];
        }
        
        Stack<Integer> stack = new Stack<>();
        for(int i = 0; i < prefixSum.length; i++) {
            if(stack.isEmpty() || prefixSum[i] < prefixSum[stack.peek()]) {
                stack.push(i);
            }
        }

        int maxLen = 0;
        for(int j = prefixSum.length - 1; j >= 0; j--) {
            while(!stack.isEmpty() && prefixSum[j] > prefixSum[stack.peek()]) {
                maxLen = Math.max(maxLen, j - stack.pop());
            }
        }
        return maxLen;
    }
}
