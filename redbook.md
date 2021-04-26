## 问题
- 重载和重写的区别
1. 重载： 发生在同一个类中，方法名必须相同，参数类型不同、个数不同、顺序不同，方法返回值和访问修饰符可以不同，发生在编译时。 　　
2. 重写： 发生在父子类中，方法名、参数列表必须相同，返回值范围小于等于父类，抛出的异常范围小于等于父类，访问修饰符范围大于等于父类；如果父类方法访问修饰符为private则子类就不能重写该方法。
Java 面向对象编程三大特性:封装、继承、多态

# 代码
# 快速排序
## 原理/思想：
1. 选择一个基线值（通常是左侧第一个）
2. 把大于基线值的数字放在基线的右边
3. 把小于基线的数字放在基线的左边
4. 分别对左右序列重复前三步骤
```python
def quicksort(arry):
    if len(arry) < 2:
        return arry
    else:
        privot = arry[0]
    less = [i for i in arry[1:] if i <= privot]
    greater = [i for i in arry[1:] if i > privot]

    return quicksort(less) + [privot] + quicksort(greater)


print(quicksort([10, 5, 2, 3]))
```
```python
def fun(array):
    odd = []  # 奇数
    even = []  # 偶数
    for i in array:
        if i % 2 == 0:
            even.append(i)
    data = quicksort(even)
    return data
def quicksort(even):
    if len(even) < 2:
        return even
    else:
        privot = even[0]
    less = [i for i in even[1:] if i <= privot]
    greater = [i for i in even[1:] if i > privot]
    return quicksort(less) + [privot] + quicksort(greater)
print(fun([1,3,4,7,5,9,4,8,6,2]))
```

```python
def twoSum1(nums, target):
    n = len(nums)
    for i in range(n):
        for j in range(i + 1, n):
            if nums[i] + nums[j] == target:
                return [i, j]
    return []

```
```python
# 给定一个非空正整数的数组，按照数组内数字重复出现次数，从高到低排序
list = [1, 1, 1, 6, 6, 7, 3, 9]
d = {}
list_sorted = []
for i in list:
    if list.count(i) > 1:
        d[i] = list.count(i)
print(d)# 根据字典值的降序排序
d_sorted = sorted(d.items(), key=lambda x: x[1], reverse=True)  # [(1, 3), (6, 2), (7, 1), (3, 1), (9, 1)]
#print(d_sorted)
for x in d_sorted:# 输出排序后的数组
    #print(x)
    for number in range(0, x[1]):
        list_sorted.append(x[0])
print("按照重复次数排序后的数字是：{}".format(list_sorted))  # [1, 1, 1, 6, 6]
list_sorted = set(list_sorted)# 第一种去重
print("按照重复次数排序后的数字是：" ,list_sorted)  # {1, 6}
list_sorted = {}.fromkeys(list_sorted)# 第二种去重
print("按照重复次数排序后的数字是：" , list_sorted.keys())# [1, 6]
```
```python
# 先把所有的不同的字母的出现字数保存在字典中，然后再遍历一遍字典，找到第一个符合条件的
def firstUniqChar(s: str) -> str:
    dic1 = {}
    k = len(s)
    for i in range(k):
        if s[i] not in dic1.keys():
            dic1.setdefault(s[i], 1)
        else:
            dic1[s[i]] += 1   # 求出所有字符在字典里的次数
    for i, v in dic1.items():
        if v == 2:
            return i
    return ' '

print(firstUniqChar('sdwewes'))
```
```python
# keys() 该方法会返回字典的所有的key
#   该方法会返回一个序列，序列中保存有字典的所有的键
d = {'name':'孙悟空','age':18,'gender':'男'}
print(d.keys())
# 通过遍历keys()来获取所有的键
for k in d.keys():
    print(k, d[k])
# values()
# 该方法会返回一个序列，序列中保存有字典的所有的值
for v in d.values():
    print(v)
# items()
# 该方法会返回字典中所有的项
# 它会返回一个序列，序列中包含有双值子序列
# 双值分别是，字典中的key和value
for k,v in d.items():
    print(k, '=', v)
 ```
