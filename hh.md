# 剑指 Offer 03. 数组中重复的数字

## 题目描述
在一个长度为 n 的数组 nums 里的所有数字都在 0～n-1 的范围内。数组中某些数字是重复的，但不知道有几个数字重复了，也不知道每个数字重复了几次。请找出数组中任意一个重复的数字。
示例 1：

输入：
[2, 3, 1, 0, 2, 5, 3]
输出：2 或 3 
 

限制：
2 <= n <= 100000

## 题解

```python
class Solution:
    def findRepeatNumber(self, nums: List[int]) -> int:
# 方法一：哈希表 set hashmap hashset dict 都是不可以重复
        a = set()
        for num in nums:
            if num in a:
                return num
            a.add(num)   # set没有append
        return -1
# ----------
#       hashmap = {}
#         for num in nums:
#             if num in hashmap:
#                 return num
#             hashmap[num] = 1      

```
