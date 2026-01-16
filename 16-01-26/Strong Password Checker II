class Solution {
    public boolean strongPasswordCheckerII(String password) {
        String letters = "abcdefghijklmnopqrstuvwxyz";
        String capital = letters.toUpperCase();
        String special = "!@#$%^&*()-+";
        boolean containsUpper = false;
        boolean containsLower = false;
        boolean containsSpecial = false;
        boolean containsNum = false;
        if(password.length() < 8){
            return false;
        }
        for(int i = 0; i<password.length(); i++){
            char c = password.charAt(i);
            if(letters.indexOf(c)!= -1){
                containsLower = true;
            }
            if(capital.indexOf(c) != -1){
                containsUpper = true;
            }
            if(c >= 48 && c <= 57){
                containsNum = true;
            }
            if(special.indexOf(c)!= -1){
                containsSpecial = true;
            }
            if(i<password.length()-1){
                if(c == password.charAt(i+1)){
                    return false;
                }
            }
        }
       


        return containsNum && containsUpper && containsLower && containsSpecial;
    }
}
