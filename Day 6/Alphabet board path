class Solution {
    public String alphabetBoardPath(String target) {
        StringBuilder path = new StringBuilder();
        int cr = 0;
        int cc = 0;
        for (int i = 0; i < target.length(); i++) {
            char ch = target.charAt(i);
            int n = ch - 'a';
            int r = n / 5; 
            int c = n % 5; 
            if (cr == r && cc == c) {
                path.append("!");
            } else if (cr == r) {
                while (cc < c) {
                    cc++;
                    path.append('R');
                }
                while (cc > c) {
                    cc--;
                    path.append('L');
                }
                path.append("!");
            } else if (cc == c) {
                while (cr < r) {
                    cr++;
                    path.append('D');
                }
                while (cr > r) {
                    cr--;
                    path.append('U');
                }
                path.append("!");
            } else {
                while (cc > c) {
                    cc--;
                    path.append('L');
                }
                while (cr < r) {
                    cr++;
                    path.append('D');
                }
                while (cr > r) {
                    cr--;
                    path.append('U');
                }
                while (cc < c) {
                    cc++;
                    path.append('R');
                }
                path.append("!");
            }
        }
        return path.toString();
    }
}
