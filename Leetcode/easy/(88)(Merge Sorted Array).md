```class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        i = m-1
        j = n-1
        r = n+m-1

        while j >=0 :
            if i >= 0 and nums1[i] > nums2[j]:
                nums1[r] = nums1[i]
                i -= 1
            else:
                nums1[r] = nums2[j]
                j -= 1
            r -= 1
        return nums1
```

# Problem
You are given two integer arrays nums1 and nums2, sorted in non-decreasing order, and two integers m and n, representing the number of elements in nums1 and nums2 respectively.

Merge nums1 and nums2 into a single array sorted in non-decreasing order.

The final sorted array should not be returned by the function, but instead be stored inside the array nums1. To accommodate this, nums1 has a length of m + n, where the first m elements denote the elements that should be merged, and the last n elements are set to 0 and should be ignored. nums2 has a length of n.

# Solution:
Runtime: O(m+n)
Example : nums1 = [1,2,3,0,0,0], nums2 = [2,3,4]
Both arrays are in ascending order. Set pointer to m, n indeces, and set a right pointer to the end of nums1 array. For each step, find greatest value and insert that into the array. 