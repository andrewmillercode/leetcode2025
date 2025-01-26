
```
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        res = nums[0] # max sum
        tMax = nums[0] # temp max
        for i in range(1,len(nums)):
            tMax = max(nums[i],tMax + nums[i])

            # if tmax > max, max = tmax
            if tMax > res: res = tMax
            # alternatively -> res = max(res,tMax)
        return res 
```
Solved using [Kadane's Algorithm](/Data%20Algorithms/Kadane's%20Algorithm.md)

Time Complexity: O(N)
Space Complexity: O(1)