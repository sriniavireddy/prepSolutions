# prepSolutions

1. Inverting a tree

    public TreeNode invertTree(TreeNode root) {
        
        if(root == null)
            return root;
        
        TreeNode temp = root.left;
        root.left = root.right;
        root.right = temp;
        
        invertTree(root.left);
        invertTree(root.right);
        
        return root;
        
    }
    
2. check if two binary trees are same

    public boolean isSameTree(TreeNode p, TreeNode q) {
        
        if(p == null && q == null)
            return true;
        else if((p == null && q != null) || (p != null && q == null))
            return false;
        else if (p.val == q.val) {
            return isSameTree(p.left, q.left) && isSameTree(p.right, q.right);
        }
        else {
            return false;
        }
 
        
    }
