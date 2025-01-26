```
import heapq

class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        # get frequency
        d = {}
        for i in nums:
            if i in d:
                d[i] += 1
                continue
            d[i] = 1
        return heapq.nlargest(k, d, key=d.get) 
            
```