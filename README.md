# 572.-Subtree-of-Another-Tree

````C#

- George Washington
- John Adams
- Thomas Jefferson

Problem: Given two non-empty binary trees s and t, check whether tree t has exactly the same structure and node values with a subtree of s. 
A subtree of s is a tree consists of a node in s and all of this node's descendants. The tree s could also be considered as a subtree of itself.

 public class MaxDepthBinaryTree
    {
        static void Main(string[] args)
        {
            TreeNode root = new TreeNode(3);
            root.left = new TreeNode(4);
            root.right = new TreeNode(5);
            root.left.left = new TreeNode(1);
            root.left.right = new TreeNode(2);

            TreeNode root2 = new TreeNode(4);
            root2.left = new TreeNode(1);
            root2.right = new TreeNode(2);
            Console.WriteLine(IsSubtree(root, root2));

            Console.ReadLine();
        }
        public static bool IsSubtree(TreeNode s, TreeNode t)
        {
            if (t == null) return true;

            if (s == null) return false;
            
            if (AreIdentical(s, t)) return true;

            return IsSubtree(s.left, t) || IsSubtree(s.right, t);
             
        }

        public static bool AreIdentical(TreeNode s, TreeNode t)
        {
            if (s == null && t == null) return true;

            if (s == null || t == null) return false;

            return s.val == t.val && AreIdentical(s.left, t.left) && AreIdentical(s.right, t.right);
        }
    } 
   public class TreeNode 
    {
       public int val;
       public TreeNode left;
       public TreeNode right;
       public TreeNode(int val=0, TreeNode left=null, TreeNode right=null) 
       {
          this.val = val;
          this.left = left;
          this.right = right;
       }
     } 



````
