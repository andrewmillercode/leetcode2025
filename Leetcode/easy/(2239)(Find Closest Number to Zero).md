```
class Solution:
    def findClosestNumber(self, nums: List[int]) -> int:
        res = nums[0]
        for i in nums:
            if abs(i) < abs(res):
                res = i
        if res < 0 and abs(res) in nums:
            return abs(res)
        return res
```
Given an integer array nums of size n, return the number with the value closest to 0 in nums. If there are multiple answers, return the number with the largest value. 

Iterate over array, if distance of i is less than answer, answer is i. 

Since problem asks for answer with the largest value, we check if a positive instance of answer exists in array, and if so, return the instance.

Time complexity: O(n)
Space Complexity: O(1)