```# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        if not root:
            return 0
        return max(self.maxDepth(root.left),self.maxDepth(root.right)) + 1 #increment by 1 higher up we go from bottom -> top in the tree```

This is a unique case where recursion is actually more efficient that dynamic programming. Because there are no redundant operations (everything is calculated exactly once), memoization won't be able to optimize this. However, deep recursion calls can lead to a stack overflow, so switching to a BFS approach can be helpful in this case. 
Note that the BFS approach performs worse than the recursive approach when the tree is wide rather than deep.

BFS sol:
```class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        if not root:
            return 0
        maxD = 0
        q = deque()
        q.append(root)

        while q:
            maxD += 1

            for _ in range(len(q)):
                curNode = q.popleft()
                if curNode.left:
                    q.append(curNode.left)
                if curNode.right:
                    q.append(curNode.right)
        return maxD
```