Solution 1 (Built-in tim sort): O(nlogn)
```
class Solution:
    def findKthLargest(self, nums: List[int], k: int) -> int:
        g = sorted(nums)
        return g[-k]
```
Solution 2 (Heap) : O(nlogk)
```
import heapq

class Solution:
    def findKthLargest(self, nums: List[int], k: int) -> int:
        # Create a min-heap to store the k largest elements
        min_heap = []
        
        # Iterate over the numbers
        for num in nums:
            heapq.heappush(min_heap, num)  # Push the current number to the heap
            if len(min_heap) > k:         # If heap size exceeds k, remove the smallest element
                heapq.heappop(min_heap)
        
        # The root of the heap (the smallest of the largest k elements) is the kth largest
        return min_heap[0]
```
Given an integer array nums and an integer k, return the kth largest element in the array.

Note that it is the kth largest element in the sorted order, not the kth distinct element.

Can you solve it without sorting?