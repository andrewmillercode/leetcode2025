```
class Solution:
    def containsNearbyDuplicate(self, nums: List[int], k: int) -> bool:
        visited = set()
        l = 0
        for r in range(len(nums)):
            if r - l > k :
                #no instance of duplicate in range of k, move left forward
                visited.remove(nums[l])
                l += 1
            if nums[r] in visited:
                return True
            visited.add(nums[r])
                
        return False
```

Time Complexity: O(N) 
Space Complexity: O(N)

Given an integer array nums and an integer k, return true if there are two distinct indices i and j in the array such that nums[i] == nums[j] and abs(i - j) <= k.

