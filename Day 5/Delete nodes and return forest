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
    public List<TreeNode> delNodes(TreeNode root, int[] to_delete) {
        Set<Integer> set = new HashSet<>();
        for (int i : to_delete) {
            set.add(i);
        }
        List<TreeNode> res = new ArrayList<>();
        if (!set.contains(root.val))
            res.add(root); 
        delete(root, set, null, res, true);
        return res;
    }

    private void delete(TreeNode cur, Set<Integer> set, TreeNode parent, List<TreeNode> res, boolean isLeft) {
        if (cur == null) return;
        delete(cur.left, set, cur, res, true);
        delete(cur.right, set, cur, res, false);
        if (set.contains(cur.val)) {
            if (cur.left != null) {
                res.add(cur.left);
                cur.left = null;
            }
            if (cur.right != null) {
                res.add(cur.right);
                cur.right = null;
            }
            if (parent != null) {
                if (isLeft) {
                    parent.left = null;
                } else {
                    parent.right = null;
                }
            }
        }
    }
}
