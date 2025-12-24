class Solution {
    public int help(String s1, String s2, int i, int j, int memo[][]){
        if(i==s1.length() || j==s2.length()) return 0;
        if(memo[i][j] != -1) return memo[i][j];
        if(s1.charAt(i)==s2.charAt(j)){
            memo[i][j] =  1+ help(s1,s2,i+1,j+1,memo);
        }else{
            memo[i][j] = Math.max(help(s1,s2,i+1,j,memo), help(s1,s2,i,j+1,memo));
        }
        return memo[i][j];
    }
    public int longestCommonSubsequence(String text1, String text2) {
        int memo[][] = new int[text1.length()+1][text2.length()+1];
        for(int i=0; i<memo.length; i++){
            Arrays.fill(memo[i],-1);
        }
        return help(text1,text2,0,0,memo);
    }
}
