#### Problem
No. 338: https://leetcode.com/problems/counting-bits/

#### Code
```python
class Solution:
    def countBits(self, num: int) -> List[int]:
        if num >= 2:
            result = [0, 1]
            curr_flag = 1
            for n in range(2, num + 1):
                if n == curr_flag * 2:
                    curr_flag = n
                    result.append(1)
                else:
                    result.append(result[n - curr_flag] + 1)
            return result
        elif num == 1:
            return [0, 1]
        
        return [0]
```