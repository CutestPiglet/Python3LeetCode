#### Problem
No. 101: https://leetcode.com/problems/symmetric-tree/

#### Code
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def isSymmetric(self, root: TreeNode) -> bool:
        if not root:
            return True
        
        return self.is_symmetric_tree(root.left, root.right)
    
    def is_symmetric_tree(self, left: TreeNode, right: TreeNode) -> bool:
        if not left and not right:
            return True
        
        if left and right and (left.val == right.val):
            is_outer_symmetric = self.is_symmetric_tree(left.left, right.right)
            is_innter_symmetric = self.is_symmetric_tree(left.right, right.left)
            return is_outer_symmetric & is_innter_symmetric
            
        return False
```