class Solution {
    public int maxDepth(Node root) {
        if (root == null)
            return 0;
        int max = 1;
        for (int i = 0; i < root.children.size(); i++)
            max = Math.max(max, 1 + maxDepth(root.children.get(i)));
        return max;
    }
}
