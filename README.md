# leetcode 938 - Range Sum of BST
 

 
```py
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
 
    def rangeSumBST(self, root: Optional[TreeNode], low: int, high: int) -> int:
        def rec(root):
            if root is not None:
                out.append(root.val) 
                rec(root.left)
                rec(root.right)
        
        out = []
        sum_out = 0
        rec(root)
        for i, v in enumerate(out):
            if v >= low and v <= high:
                sum_out += v        
        return sum_out 
```

