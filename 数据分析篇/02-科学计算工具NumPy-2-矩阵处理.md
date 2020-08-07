## 一 ndarray的矩阵处理

#### 1.1 ndarray的矩阵运算

矢量运算：相同大小的数组间运算应用在元素上。  

数组是编程中的概念，矩阵、矢量是数学概念。在计算机编程中，矩阵可以用数组形式定义，矢量可以用结构定义!  

```py
# 矢量与矢量运算
arr = np.array([[1, 2, 3],
                [4, 5, 6]])

print("元素相乘：")
print(arr * arr)

print("矩阵相加：")
print(arr + arr)
```

矢量和标量运算："广播" - 将标量"广播"到各个元素。
```py
# 矢量与标量运算
print(1. / arr)
print(2. * arr)
```

#### 1.2 ndarray的索引与切片

一维数组的索引与切片（与Python的列表索引功能相似）：
```py
# 一维数组
arr1 = np.arange(10)
print(arr1)
print(arr1[2:5])
 ```

多维数组的索引与切片：`arr[1,1] 等价 arr[1][1]`，`[:] 代表某个维度的数据`
```py
# 多维数组
arr2 = np.arange(12).reshape(3,4)
print(arr2)

print(arr2[1])

print(arr2[0:2, 2:])

print(arr2[:, 1:3])
```

条件索引:布尔值多维数组：arr[condition]，condition也可以是多个条件组合。  

注意，多个条件组合要使用 & | 连接，而不是Python的 and or。  

```py
# 条件索引

# 找出 data_arr 中 2005年后的数据
data_arr = np.random.rand(3,3)
print(data_arr)

year_arr = np.array([[2000, 2001, 2000],
                     [2005, 2002, 2009],
                     [2001, 2003, 2010]])

is_year_after_2005 = year_arr >= 2005
print(is_year_after_2005, is_year_after_2005.dtype)

filtered_arr = data_arr[is_year_after_2005]
print(filtered_arr)

#filtered_arr = data_arr[year_arr >= 2005]
#print(filtered_arr)

# 多个条件
filtered_arr = data_arr[(year_arr <= 2005) & (year_arr % 2 == 0)]
print(filtered_arr)
```

#### 1.3 ndarray的维数转换

二维数组直接使用转换函数：transpose()  

高维数组转换要指定维度编号参数 (0, 1, 2, …)，注意参数是元组  

```py
arr = np.random.rand(2,3)    # 2x3 数组
print(arr)    
print(arr.transpose()) # 转换为 3x2 数组


arr3d = np.random.rand(2,3,4) # 2x3x4 数组，2对应0，3对应1，4对应3
print(arr3d)
print(arr3d.transpose((1,0,2))) # 根据维度编号，转为为 3x2x4 数组
```
