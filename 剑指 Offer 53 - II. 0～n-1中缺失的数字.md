# 剑指 Offer 53 - II. 0～n-1中缺失的数字
## 题目描述
一个长度为n-1的递增排序数组中的所有数字都是唯一的，并且每个数字都在范围0～n-1之内。在范围0～n-1内的n个数字中有且只有一个数字不在该数组中，请找出这个数字。
示例 1:
输入: [0,1,3]
输出: 2

示例 2:
输入: [0,1,2,3,4,5,6,7,9]
输出: 8
## 题解
```python
#第一种JAVA解法：暴力求解，所以我们只需要从前往后逐个遍历，少了哪个就返回哪个
# 首先要理解这个题目：题目意思就是有一个数组长度为n，数组里面的数的范围是0~n，数组只能存储n个数，但是数字确有n+1个，所以肯定有一个漏掉的
# 而且数组是递增的，那么就只有两种情况[0....][1....]，要么是0开头，要么是1开头
# 其实0开头和1开头都会发生一种情况-》数组下标和数不对应（相等），那么此时漏掉的数就是下标
# 另外一种情况就是每个数和其下标都是相等的，那么漏掉的数就是数组的长度
# class Solution {
#     public int missingNumber(int[] nums) {

#         for(int i = 0; i < nums.length; i ++) {
#             if(nums[i] != i) {
#                 return i;
#             }
#         }
#         return nums.length;
#     }
# }
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        i, j = 0, len(nums) - 1
        while i <= j:
            m = (i + j) // 2
            if nums[m] == m: i = m + 1
            else: j = m - 1
        return i
       
```
