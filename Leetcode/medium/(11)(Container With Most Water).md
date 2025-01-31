```
class Solution:
    def maxArea(self, height: List[int]) -> int:
        # Plan: 
        # Maximize base and height

        i = 0
        j = len(height) - 1
        res = 0 
        
        while i < j:
            b = j - i
            h = min(height[i], height[j])
            area = b * h
            res = max(area, res)

            if height[i] < height[j]:
                i += 1
            else: 
                j -= 1
            


        return res
```

Keep track of maximum area. Sliding window approach. If one of the heights are smaller, then move them for a taller one. This ensures more water stays in the container.
