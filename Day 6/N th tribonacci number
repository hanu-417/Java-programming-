class Solution {
    public int tribonacci(int n) {
        int f=0,s=1,t=1;
        int i=3;
        int fo=0;
        while(i<=n)
        {
            fo=f+s+t;
            f=s;
            s=t;
            t=fo;
            i++;
        }
        if(n<1)
        return 0;
        else if(n<3)
        return 1;
        else
        return fo;
    }
}
