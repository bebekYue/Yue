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
```python
# 方法二：暴力求解
    def findRepeatNumber(self, nums: List[int]) -> int:
           for i in range(len(nums)):
                for j in range(i+1,len(nums)):
                    if nums[i] == nums[j]:
                        return nums[i]
```
```python
# 方法三：原地置换
     def findRepeatNumber(self, nums: List[int]) -> int:
        n = len(nums)
        for i in range(n):
            while not nums[i] == i:
                j = nums[i]
                if nums[j] == j:
                    return j
                nums[i], nums[j] = nums[j], nums[i]
```
```python
# 方法三：原地置换
     def findRepeatNumber(self, nums: List[int]) -> int:
        n = len(nums)
        for i in range(n):
            while not nums[i] == i:
                j = nums[i]
                if nums[j] == j:
                    return j
                nums[i], nums[j] = nums[j], nums[i]
```
```python
# 排序先排序，然后看相邻元素是否有相同的，有直接return。 不过很慢，时间O(nlogn)了，空间O(1)
     def findRepeatNumber(self, nums: List[int]) -> int:
        nums.sort()
        pre = nums[0]
        n = len(nums)
        for index in range(1, n):
            if pre == nums[index]:
                return pre
            pre = nums[index]
-----------简便写法
        nums.sort()
        for i in range(0,len(nums)):
            if nums[i] == nums[i+1]:
                return nums[i]
```
