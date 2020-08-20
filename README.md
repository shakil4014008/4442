# leetcode 938 - Range Sum of BST

## Java
```Java
```

## C#
#### Recursive Implementation
```C#

static int RangeSumBST(TreeNode root, int L, int R)
{
    if (root == null) return 0;
    if (root.val >= L && root.val <= R)
        return root.val + RangeSumBST(root.left, L, R) + RangeSumBST(root.right, L, R);
    else if (root.val < L)
        return RangeSumBST(root.right, L, R);
    else
        return RangeSumBST(root.left, L, R);
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
