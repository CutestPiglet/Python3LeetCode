#### Problem
No. 21: https://leetcode.com/problems/merge-two-sorted-lists/

#### Code
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
        dummy = result = ListNode(None)
        
        while l1 and l2:
            if l1.val <= l2.val:
                result.next = l1
                l1 = l1.next
            else:
                result.next = l2
                l2 = l2.next
            
            result = result.next
        
        result.next = l1 or l2
        
        return dummy.next
```