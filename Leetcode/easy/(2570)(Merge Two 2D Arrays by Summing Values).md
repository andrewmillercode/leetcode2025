```class Solution:
    def mergeArrays(self, nums1: List[List[int]], nums2: List[List[int]]) -> List[List[int]]:
        """
        Return an array of subarrays such that each subarray has an [id,val].
        Ascending by ID.
        If ID present in nums1 & nums2, resulting val is v1+v2

        Both arrays are in ascending order, so we can just have two pointers and increment one if one is less than the other
        """
        res = []
        j = k = 0
        while j < len(nums1) and k < len(nums2):
            if nums1[j][0] < nums2[k][0] :
                #index comparison
                res.append([nums1[j][0], nums1[j][1]])
                j += 1
            elif nums2[k][0] < nums1[j][0]:
                res.append([nums2[k][0], nums2[k][1]])
                k += 1
            else:
                #same index. add the resulting vals
                res.append([nums1[j][0], nums1[j][1] + nums2[k][1]])
                j += 1
                k += 1
        res.extend(nums1[j:])
        res.extend(nums2[k:])
        
        return res```