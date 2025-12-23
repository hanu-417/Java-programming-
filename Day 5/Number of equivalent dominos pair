class Solution {
    public int numEquivDominoPairs(int[][] dominoes) {
        int n = dominoes.length, count = 0;

        HashMap<Integer,Integer> dict1 = new HashMap<>();

        for (int i = 0; i < n; i++){
            int min_val = Math.min(dominoes[i][0],dominoes[i][1]);
            int max_val = Math.max(dominoes[i][0],dominoes[i][1]);
            int val = min_val*10 + max_val;
            if (dict1.containsKey(val)){
                count += dict1.get(val);
            }
            if (!dict1.containsKey(val)){
                dict1.put(val,1);
            } else {
                dict1.put(val,dict1.get(val)+1);
            }
        }

        return count;
    }
}
