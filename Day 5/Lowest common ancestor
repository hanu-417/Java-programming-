/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    public TreeNode lcaDeepestLeaves(TreeNode root) {

        Queue<TreeNode> q = new LinkedList<>();
        q.add(root);

        ArrayList<TreeNode> lastList = new ArrayList<>();

        // BFS to find the deepest level
        while (!q.isEmpty()) {
            int size = q.size();
            lastList.clear(); // start a new level

            for (int i = 1; i <= size; i++) {
                TreeNode node = q.remove();
                lastList.add(node);

                if (node.left != null) {
                    q.add(node.left);
                }
                if (node.right != null) {
                    q.add(node.right);
                }
            }
        }

        // leftmost and rightmost deepest nodes
        TreeNode left = lastList.get(0);
        TreeNode right = lastList.get(lastList.size() - 1);

        // find LCA of these two deepest nodes
        return lca(root, left, right);
    }

    // Standard LCA for binary tree
    public TreeNode lca(TreeNode root, TreeNode p, TreeNode q){
        if(root == null) {
            return null;
        }

        if(root == p || root == q){
            return root;
        }

        TreeNode leftAns = lca(root.left, p ,q);
        TreeNode rightAns = lca(root.right, p ,q);

        if(leftAns != null && rightAns != null){
            return root;
        }
        if(leftAns != null && rightAns == null){
            return leftAns;
        }
        if(leftAns == null && rightAns != null){
            return rightAns;
        }
        else{
            return null;
        }
    }
}
