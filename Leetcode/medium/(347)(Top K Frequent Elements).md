```

class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        return [x for x, y in Counter(nums).most_common()][0:k]

```

Find frequency for each unique number, then find top K most frequent based on the count
