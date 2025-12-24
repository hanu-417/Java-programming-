class SnapshotArray {


    // <time> -> Map<key, val>
    TreeMap<Integer, List<Integer>> snapShotMap2;


    // <key> -> TreeMap<time, val>
    List<TreeMap<Integer, Integer>> snapShotList;

    int snapshotId;

    // current map: Map<key, val>
    List<Integer> list;

    public SnapshotArray(int length) {
        this.snapshotId = 0;
        this.snapShotList = new ArrayList<>(length);
        // fill it with 0s
        for (int i = 0; i < length; i++) {
            // init index `i` (to a new TreeMap)
            this.snapShotList.add(new TreeMap<>());
            // set value of index `i` to 0
            this.set(i, 0);
        }
    }

    public void set(int index, int val) {
        var snapshotList = this.snapShotList.get(index);
        snapshotList.put(snapshotId, val);
        // `snapshotMap` should be mutated already, no need to set explicitely
    }

    public int snap() {
        var originalSnapshotId = this.snapshotId;
        snapshotId++;
        // for (int i = 0; i < snapShotList.size(); i++) {
        //     // create a snapshot for each index of the array snapshotList
        //     var snapshotTimeItem = snapShotList.get(i);
        //     
        //     // snapshotTimeItem.put(this.snapshotId, snapshotTimeItem.get(originalSnapshotId));
        //                 snapshotTimeItem.put(this.snapshotId, snapshotTimeItem.lastEntry().getValue());
        // }
        return originalSnapshotId;
    }

    public int get(int index, int snapId) {
        var snapshotTimeItem = snapShotList.get(index);
        return snapshotTimeItem.floorEntry(snapId).getValue();
    }



}

/**
 * Your SnapshotArray object will be instantiated and called as such:
 * SnapshotArray obj = new SnapshotArray(length);
 * obj.set(index,val);
 * int param_2 = obj.snap();
 * int param_3 = obj.get(index,snap_id);
 */
