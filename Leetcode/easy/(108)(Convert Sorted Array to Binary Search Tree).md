```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def sortedArrayToBST(self, nums: List[int]) -> Optional[TreeNode]:
        
        if not nums : return None
        mid = len(nums) // 2

        return TreeNode(
            nums[mid],
            self.sortedArrayToBST(nums[:mid]),self.sortedArrayToBST(nums[mid+1:])
        )
```

## Recursive solution, get midpoint of each subarray and split it in half, continue recursively.