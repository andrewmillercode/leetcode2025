```
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        return len(set(nums)) < len(nums)
```
A set can only have distinct/different elements. By turning an array with duplicate elements into a set, we remove elements from the array. Therefore, if the length of the set is less than the length of the array, duplicate elements exist. 

Time Complexity: o(n)
Space Complexity: o(n)