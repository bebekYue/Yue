# 剑指 Offer 28. 对称的二叉树
## 题目描述
请实现一个函数，用来判断一棵二叉树是不是对称的。如果一棵二叉树和它的镜像一样，那么它是对称的。

例如，二叉树 [1,2,2,3,4,4,3] 是对称的。

    1
   / \
  2   2
 / \ / \
3  4 4  3
但是下面这个 [1,2,2,null,3,null,3] 则不是镜像对称的:

    1
   / \
  2   2
   \   \
   3    3

 

示例 1：
输入：root = [1,2,2,3,4,4,3]
输出：true

示例 2：
输入：root = [1,2,2,null,3,null,3]
输出：false


## 题解
<img width="619" alt="截屏2021-08-27 下午11 14 55" src="https://user-images.githubusercontent.com/49756528/131150036-59f2addc-adaa-4a09-ac44-641abc0f9515.png">
<img width="757" alt="截屏2021-08-27 下午11 15 06" src="https://user-images.githubusercontent.com/49756528/131150173-482be5e8-1e14-4c6b-96ed-c20090130a4d.png">

```python
    def isSymmetric(self, root: TreeNode) -> bool:
        def recur(L,R):       
            if not L and not R:return True
            if not L or not R or L.val != R.val:return False 
            return recur(L.left, R.right) and recur(L.right, R.left)

        return recur(root.left,root.right) if root else True


节点为空的情况有：
左节点为空，右节点不为空，不对称，return false
左不为空，右为空，不对称 return false
左右都为空，对称，返回true

此时已经排除掉了节点为空的情况，那么剩下的就是左右节点不为空：
左右都不为空，比较节点数值，不相同就return false


```
