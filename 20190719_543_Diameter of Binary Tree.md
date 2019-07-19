#### Problem
No. 543: https://leetcode.com/problems/diameter-of-binary-tree/

#### Code
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def diameterOfBinaryTree(self, root: TreeNode) -> int:
        self.result = 0
        
        self.calculate_max_diameter(root)
        
        return self.result
    
    def calculate_max_diameter(self, root):
        if not root:
            return 0

        left_depth = self.calculate_max_diameter(root.left)
        right_depth = self.calculate_max_diameter(root.right)
        
        # diameter
        self.result = max(self.result, left_depth + right_depth)
        
        # depth
        return max(left_depth, right_depth) + 1
```