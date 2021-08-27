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
![Uploading 截屏2021-08-27 下午11.15.06.png…]()

```python
    def isSymmetric(self, root: TreeNode) -> bool:
        def recur(L,R):       
                if not root:
                    return false
                    
                if not L and not R:return True
                if not L or not R or L.val != R.val:return False 
                # return recur(L.right, R.left) and return(L.left, R.right) 不可以这样写
                return recur(L.left, R.right) and recur(L.right, R.left)

        return recur(root.left,root.right)

```
