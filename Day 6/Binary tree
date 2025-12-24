class Solution {
    TreeNode xNode = null;

    // Counts nodes in the tree BUT also finds the node with value x.
    // When the node x is found, store it in xNode and return 0 (so it isn't counted in upper region).
    public int noOfNodes(TreeNode root, int x){
        if(root == null) return 0;

        // Found the node chosen by Player 1
        if(root.val == x){
            xNode = root;
            return 0;   // do not count x when calculating upper nodes
        }

        // Leaf node contributes 1
        if(root.left == null && root.right == null) return 1;

        // Count nodes in left + right + current node
        return noOfNodes(root.left, x) + noOfNodes(root.right, x) + 1;
    }

    public boolean btreeGameWinningMove(TreeNode root, int n, int x) {

        // Nodes above x (the parent region)
        int upperNodesCount = noOfNodes(root, x);

        // Nodes in x's left subtree
        int leftNodesCount = noOfNodes(xNode.left, x);

        // Nodes in x's right subtree
        int rightNodesCount = noOfNodes(xNode.right, x);

        // Special case: if x is the root (no upper nodes)
        if(upperNodesCount == 0){
            // If left and right are equal, second player can't dominate
            if(leftNodesCount == rightNodesCount) return false;
            else return true;  // Otherwise second player can win
        }

        // Case 1: upper region has more nodes than both left+right+x
        boolean case1 = (upperNodesCount > leftNodesCount + rightNodesCount + 1);

        // Case 2: left subtree has more nodes than upper+right+x
        boolean case2 = (leftNodesCount > upperNodesCount + rightNodesCount + 1);

        // Case 3: right subtree has more nodes than upper+left+x
        boolean case3 = (rightNodesCount > leftNodesCount + upperNodesCount + 1);

        // If any region is strictly larger, second player wins
        return case1 || case2 || case3;
    }
}
