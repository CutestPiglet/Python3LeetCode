#### Problem
No. 448: https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/

#### Code
```python
class Solution:
    def findDisappearedNumbers(self, nums: List[int]) -> List[int]:
        if not nums:
            return nums
        
        result = list(range(1, len(nums) + 1))
        for num in nums:
            result[num - 1] = 0

        return [r for r in result if r > 0]
```
