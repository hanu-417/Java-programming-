class Solution {
    public int movesToMakeZigzag(int[] nums) {
        int n = nums.length;
        int even =0;
        int odd = 0;
        for(int i=0;i<n;i++){
        int l = (i>0) ? nums[i-1] : Integer.MAX_VALUE;
        int r = (i<n-1) ? nums[i+1] : Integer.MAX_VALUE;
        int res = Math.max(0,nums[i] - Math.min(l,r)+1);
        if(i%2==0){
            even = even + res;
        }
        else{
            odd = odd + res;
        }
        }
        return Math.min(even,odd);
    }
}
