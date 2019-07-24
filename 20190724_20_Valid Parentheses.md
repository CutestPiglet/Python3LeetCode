#### Problem
No. 20: https://leetcode.com/problems/valid-parentheses/

#### Code
```python
class Solution:
    def isValid(self, s: str) -> bool:
        parenthesis_dict = {
            '(': ')',
            '{': '}',
            '[': ']',
        }
        
        stack = []
        for c in s:
            if c in parenthesis_dict:
                stack.append(c)
            else:
                if not stack or c != parenthesis_dict[stack.pop()]:
                    return False

        return stack == []
```