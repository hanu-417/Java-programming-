class Solution {
    public int[] corpFlightBookings(int[][] bookings, int n) {
        int dif[]=new int[n];
        for (int i=0;i<bookings.length;i++){
            int s=bookings[i][0]-1;
            int e=bookings[i][1]-1;
            int v=bookings[i][2];
            dif[s]+=v;
            if (e+1<n)dif[e+1]-=v;
        }
        int res[]=new int [n];
        res[0]=dif[0];
        for (int i=1;i<n;i++){
            res[i]=res[i-1]+dif[i];
        }
        return res;
    }
}
