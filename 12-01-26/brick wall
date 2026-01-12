class Solution {
    public int leastBricks(List<List<Integer>> wall) {
        //map way
        int n=wall.size(),res=n;
        Map<Long,Integer> map = new HashMap<>();
        for(List<Integer> l:wall){
            long p=0;
            for(int i=0;i<l.size()-1;i++){
                p+=l.get(i);
                // if(p==n) break;
                int t = map.getOrDefault(p,0)+1;
                if(n-t < res) res=n-t;
                map.put(p,t);
            }
        }
        return res;
    }
}
