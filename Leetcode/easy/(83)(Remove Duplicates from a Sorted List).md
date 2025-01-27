```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def deleteDuplicates(self, head: Optional[ListNode]) -> Optional[ListNode]:
        temp = head
        while temp:
            if temp.next and temp.next.val == temp.val:
                # duplicate
                temp.next = temp.next.next
                continue
            temp = temp.next
        return head
```

Time Complexity : O(N)

Space Complexity: O(1)