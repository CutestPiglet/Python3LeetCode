#### Problem
No. 538: https://leetcode.com/problems/convert-bst-to-greater-tree/

#### Code
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def __init__(self):
        self.sum = 0
            
    def convertBST(self, root: TreeNode) -> TreeNode:
        if root:
            self.convertBST(root.right)
            
            root.val += self.sum
            self.sum = root.val
            
            self.convertBST(root.left)
        
        return root
```