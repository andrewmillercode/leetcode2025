```
class Solution:
    def isSymmetric(self, root: Optional[TreeNode]) -> bool:
        def f(left,right):
            if not left and not right:
                return True
            if not left or not right:
                return False
            return left.val == right.val and f(left.left,right.right) and f(left.right,right.left)
    
        return f(root.left,root.right)
```
recursive dfs