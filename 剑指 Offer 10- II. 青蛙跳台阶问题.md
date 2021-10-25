# 剑指 Offer 10- II. 青蛙跳台阶问题
## 题目描述
<img width="1001" alt="截屏2021-10-25 下午10 51 00" src="https://user-images.githubusercontent.com/49756528/138718478-950648fc-1dc4-4cad-b4ac-76841a61d0a6.png">

## 题解
```python
class Solution(object):
    def numWays(self, n):
        """
        :type n: int
        :rtype: int
        """
        a,b = 1,1
        for i in range(n):
           a,b = b,a+b
        return a % 1000000007
        # 1000000007是一个质数（素数），对质数取余能最大程度避免结果冲突/重复

```
<img width="879" alt="截屏2021-10-25 下午10 52 48" src="https://user-images.githubusercontent.com/49756528/138718843-1cdd113b-ce0b-4e5b-98dc-6e9bda42fe35.png">
