#### Problem
No. 70: https://leetcode.com/problems/climbing-stairs/

#### Code
```python
class Solution:
    def climbStairs(self, n: int) -> int:
        i, j = 0, 1
        
        for _ in range(n):
            i, j = j, i + j
            
        return j
```