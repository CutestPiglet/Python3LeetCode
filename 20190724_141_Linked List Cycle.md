#### Problem
No. 141: https://leetcode.com/problems/linked-list-cycle/

#### Code
```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def hasCycle(self, head):
        """
        :type head: ListNode
        :rtype: bool
        """
        
        try:
            nxt = head.next
            while head != nxt:
                head = head.next
                nxt = nxt.next.next
            return True
        except:
            return False
```