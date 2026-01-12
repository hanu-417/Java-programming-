class Solution {
    public boolean checkRecord(String s) {
        
        int n = s.length();
        
        int count = 0;
        
        for(int i = 1;i<n-1;i++){
             if((s.charAt(i-1) == 'L' && s.charAt(i) == 'L') && s.charAt(i+1) == 'L'){
                return false;
            }
        }
        
        for(char ch:s.toCharArray()){
            count+= ch == 'A' ? 1:0;
        }
        
        if(count <= 1) return true;
        return false;
    }
}
