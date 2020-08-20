# leetcode 938 - Range Sum of BST
 

## C#
#### Recursive Implementation
```C#

/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     public int val;
 *     public TreeNode left;
 *     public TreeNode right;
 *     public TreeNode(int val=0, TreeNode left=null, TreeNode right=null) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
public class Solution {
     int sum = 0;
    public int RangeSumBST(TreeNode root, int L, int R) {
     
        if(root == null) return 0;
        
       
        if(root!= null){
            
            if(root.val>=L && root.val<=R){
             //Console.WriteLine(root.val);                
              //  Console.Write("sum="+sum);
              sum +=root.val;    
                
            }
            
            
            if(root.left != null){
                RangeSumBST(root.left, L, R);
            }
            
            if(root.right != null){
                RangeSumBST(root.right, L, R);
            }
        }
        
        
        
        return sum;
    }
}
```
#### Iterative Implementation
```C#
static int RangeSumBST(TreeNode root, int L, int R)
{
    int sum = 0;
    Stack<TreeNode> stack = new Stack<TreeNode>();
    stack.Push(root);
    while(stack.Count > 0)
    {
        var node = stack.Pop();
        if(node != null)
        {
            if (L <= node.val && node.val <= R)
                sum += node.val;
            if (L < node.val)
                stack.Push(node.left);
            if (node.val < R)
                stack.Push(node.right);
        }
    }
    return sum;
}
```

## Python
```Python
```

## Complexity Analysis

* Time Complexity: O(N), where N is the number of nodes in the tree.
* Space Complexity: O(H), where HH is the height of the tree.
