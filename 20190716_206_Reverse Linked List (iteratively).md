#### Problem
No. 206: https://leetcode.com/problems/reverse-linked-list/

#### Code
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def reverseList(self, head: ListNode) -> ListNode:
        previous = None
        
        while head:
            temp = head.next
            head.next = previous
            previous = head
            head = temp
            
        return previous
```