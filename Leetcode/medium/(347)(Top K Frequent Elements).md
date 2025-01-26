Solution 1 (lengthier w/ heap):
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
Solution 2 (one liner):

class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        return [x for x, y in Counter(nums).most_common()][0:k]

```


Find frequency for each unique number, then find top K most frequent based on the count