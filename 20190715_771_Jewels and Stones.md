#### Problem
No. 771: https://leetcode.com/problems/jewels-and-stones/

#### Code
```python
class Solution:
    def numJewelsInStones(self, J: str, S: str) -> int:
        return sum(S.count(j) for j in J)
```

