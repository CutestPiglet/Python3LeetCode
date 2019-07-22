#### Problem
No. 53: https://leetcode.com/problems/maximum-subarray/

#### Code
```python
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        if not nums:
            return 0
        
        cur_sum = max_sum = float('-inf')
        for num in nums:
            cur_sum = max(num, cur_sum + num)
            max_sum = max(max_sum, cur_sum)
            
        return max_sum
```