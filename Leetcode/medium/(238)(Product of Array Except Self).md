```
class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        answer = [1] * len(nums)

        prefix = 1
        for i in range(len(nums)):
            answer[i] = prefix
            prefix *= nums[i]
        # prefix is the product of values to Left
        # iter nums backwards, keep prod of values to right, mul answer by prod
        suffix = 1
        for i in range(len(nums)-1, -1, -1):
            answer[i] *= suffix
            suffix *= nums[i]
        
        return answer

```
Time Complexity: O(N) 
Space Complexity : O(N)