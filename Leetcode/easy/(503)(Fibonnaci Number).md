```
class Solution:
    def fib(self, n: int) -> int:
        if n == 0:
            return 0
        if n == 1 or n == 2:
            return 1 
        res = [1] * (n+1)
        res[1] = 1
        res[2] = 1
        for i in range(3,n+1):
            res[i] = res[i-1] + res[i-2]
        return res[n]

```
Bottom-up approach
O(N) time
O(N) space (recreate values)

Alternative (o(1) space complexity)
```
class Solution:
    def fib(self, n: int) -> int:
        if n == 0:
            return 0
        if n == 1 or n == 2:
            return 1 
        
        res = 1
        a = 1 
        b = 1
        
        for i in range(3,n+1):
            res = a+b
            a = b
            b = res
           
        return res
```