# Kadane's Algorithm
Primarily used to find the contiguous subarray within a 1D array that has the largest sum.
- Time Complexity: O(N) Linear
- Space Complexity: O(1) Constant
```
def maxSubarraySum(arr):

    res = arr[0]
    maxEnding = arr[0]

    for i in range(1, len(arr)):
    
        # Find the maximum sum ending at index i by either extending 
        # the maximum sum subarray ending at index i - 1 or by
        # starting a new subarray from index i
        maxEnding = max(maxEnding + arr[i], arr[i])
        
        # Update res if maximum subarray sum ending at index i > res
        res = max(res, maxEnding)
    
    return res

arr = [2, 3, -8, 7, -1, 2, 3]
print(maxSubarraySum(arr)) -> 11
```