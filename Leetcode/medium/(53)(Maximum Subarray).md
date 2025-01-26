
```
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        maxEnding = nums[0] 
        res = nums[0]

        for i in range(1, len(nums)):

            if maxEnding < 0: # This means the current subarray sum is in the negatives
                maxEnding = 0 # Start a new subarray if it's in the negative, as 0 is greater than any negative

            maxEnding += nums[i] # Add to the sum

            if res < maxEnding: # To return the maximum sum, check if the current subarray sum is greater than res
                res = maxEnding

        return res
            
            
```
Solved using [Kadane's Algorithm](/Data%20Algorithms/Kadane's%20Algorithm.md)

Time Complexity: O(N)
Space Complexity: O(1)
