#### Problem
No. 581: https://leetcode.com/problems/shortest-unsorted-continuous-subarray/

#### Code
```python
class Solution:
    def findUnsortedSubarray(self, nums: List[int]) -> int:
        if len(nums) < 2:
            return 0
        
        prev, end = nums[0], 0
        for index, num in enumerate(nums):
            if num < prev:
                end = index
            else:
                prev = num

        start = len(nums) - 1
        prev = nums[start]
        for i in range(len(nums) - 1, -1, -1):
            if prev < nums[i]:
                start = i
            else:
                prev = nums[i]
        
        return end - start + 1 if end else 0
```