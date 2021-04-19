# 剑指 Offer 53 - I. 在排序数组中查找数字 I
## 题目描述
统计一个数字在排序数组中出现的次数。
示例 1:
输入: nums = [5,7,7,8,8,10], target = 8
输出: 2

示例 2:
输入: nums = [5,7,7,8,8,10], target = 6
输出: 0
 
## 题解
```python
class Solution:
  def search(self, nums: List[int], target: int) -> int:
        dic1 = {}
        k = len(nums)
        for i in range(k):
            if nums[i] not in dic1.keys():
                dic1.setdefault(nums[i], 1)
            else:
                dic1[nums[i]] +=1
        for i, v in dic1.items():
            if i == target:
                return v       
        return 0
```

```python
class Solution:
  def search(self, nums: List[int], target: int) -> int:
        dict={}
        if target in nums:
            for i in nums:
                if i not in dict:
                    dict[i]=1
                else:
                    dict[i]+=1
            return dict[target]
        else:return 0

```
