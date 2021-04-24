# 快速排序
## 思想
```python
def quicksort(arry):
  if len(arry) < 2:
    return array
  else:
  privot = arry[0]
  less =[i for i in array[1:] if i <= privot]
  greater =[i for i in array[1:] if i>privot]
  
  return quicksort(less) +[privot] +quicksort(gerater)
print quicksort([10,5,2,3])
```
