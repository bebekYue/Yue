# 剑指 Offer 39. 数组中出现次数超过一半的数字
## 题目描述
数组中有一个数字出现的次数超过数组长度的一半，请找出这个数字。
你可以假设数组是非空的，并且给定的数组总是存在多数元素。

示例 1:
输入: [1, 2, 3, 2, 2, 2, 5, 4, 2]
输出: 2

## 题解
```python
class Solution:
#     def majorityElement(self, nums: List[int]) -> int:
#         # for i in nums:
#         #     if nums.count(i) > (len(nums)/2):
#         #         return i
#         # return 0
#         if not nums:   # 取中间数
#             return None
#         nums.sort()
#         return nums[len(nums) // 2]
# -------------------------- 摩尔投票法：
# 算法流程:
# 初始化： 票数统计 votes = 0 ， 众数 x；
# 循环： 遍历数组 nums 中的每个数字 num ；
# 当 票数 votes 等于 0 ，则假设当前数字 num 是众数；
# 当 num = x 时，票数 votes 自增 1 ；当 num != x 时，票数 votes 自减 1 ；
# 返回值： 返回 x 即可；         
# class Solution:
#     def majorityElement(self, nums: List[int]) -> int:
#         votes = 0
#         for num in nums:
#             if votes == 0: 
#                 x = num
#             if num == x:
#                 votes += 1            
#             else:
#                  -1
#         return x
# ---------------------------哈希表方法:字典这种数据结,也就是哈希表来进行查找.
# 开始遍历整个数组,如果当前数字没有在字典中,就把它加入进去,如果在字典中,则把它的数量加 1 
# 接着判断下它的数量是否是大雨整个数组的一半,如果是的话,则直接返回当前数值,否则,继续遍历.
# 由于字典的查找时间复杂度为O(1),所以总的时间复杂度为O(n),空间复杂度为O(n)
def majorityElement(nums):
    if not nums:
        return None
    if len(nums) == 1:
        return nums[0]
    write = {}
    for i in nums:
        if i not in write:
            write[i] = 1   # 拿到的是value值，如让key为1的value变成1，{1：1}
        else:
            write[i] += 1  # 拿到的是value值，如让key为3的value变成2，{3：2}，value值是数字出现的次数
            if write[i] > (len(nums) / 2):
                return i
    return None  # 如果没有超过一半的数就是为none



    
```
