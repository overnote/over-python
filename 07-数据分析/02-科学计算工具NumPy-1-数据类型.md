## 一 Numpy简介

Numpy（Numerical Python）：提供了一个在Python中做科学计算的基础库，重在数值计算，主要用于多维数组（矩阵）处理的库。用来存储和处理大型矩阵，比Python自身的嵌套列表结构要高效的多。本身是由C语言开发，是个很基础的扩展，Python其余的科学计算扩展大部分都是以此为基础。  

Numpy主要功能：
- 高性能科学计算和数据分析的基础包
- ndarray，多维数组（矩阵），具有矢量运算能力，快速、节省空间
- 矩阵运算，无需循环，可完成类似Matlab中的矢量运算
- 线性代数、随机数生成

Scipy ：基于Numpy提供了一个在Python中做科学计算的工具集，专为科学和工程设计的Python工具包。主要应用于统计、优化、整合、线性代数模块、傅里叶变换、信号和图像处理、常微分方程求解、稀疏矩阵等，在数学系或者工程系相对用的多一些，和数据处理的关系不大。

## 二 ndarray

#### 2.1 ndarray简介 

ndarray数组(N Dimension Array)是一个多维的数组对象（矩阵），称为ndarray，具有矢量算术运算能力和复杂的广播能力，并具有执行速度快和节省空间的特点。  

注意：ndarray的下标从0开始，且数组里的所有元素必须是相同类型  

ndarray拥有的属性：
- ndim属性：维度个数
- shape属性：维度大小
- dtype属性：数据类型

#### 2.2 ndarray的随机创建

通过随机抽样 (numpy.random) 生成随机数据：
```py
import numpy as np

# 生成指定维度大小（3行4列）的随机多维浮点型数据（二维），rand固定区间0.0 ~ 1.0
arr = np.random.rand(3, 4)
print(arr)
print(type(arr))                            # <class 'numpy.ndarray'>

# 生成指定维度大小（3行4列）的随机多维整型数据（二维），randint()可以指定区间（-1, 5）
arr = np.random.randint(-1, 5, (3, 4))
print(arr)
print(type(arr))

# 生成指定维度大小（3行4列）的随机多维浮点型数据（二维），uniform()可以指定区间（-1, 5）
arr = np.random.uniform(-1, 5, (3, 4))
print(arr)
print(type(arr))

print('维度个数: ', arr.ndim)
print('维度大小: ', arr.shape)
print('数据类型: ', arr.dtype)
```

#### 2.3 ndarray的序列创建

np.array(collection为序列型对象list、嵌套序列对象list of list)：
```py
# list序列转换为 ndarray
lis = range(10)
arr = np.array(lis)

print(arr)            # ndarray数据
print(arr.ndim)        # 维度个数
print(arr.shape)    # 维度大小

# list of list嵌套序列转换为ndarray
lis_lis = [range(10), range(10)]
arr = np.array(lis_lis)

print(arr)            # ndarray数据
print(arr.ndim)        # 维度个数
print(arr.shape)    # 维度大小
```

np.zeros():指定大小的全0数组。注意：第一个参数是元组，用来指定大小，如(3, 4)。  
np.ones():指定大小的全1数组。注意：第一个参数是元组，用来指定大小，如(3, 4)。  
np.empty():初始化数组，不是总是返回全0，有时返回的是未初始的随机值（内存里的随机值）。  

np.arange() 和 reshape():arange() 类似 python 的 range() ，创建一个一维 ndarray 数组。reshape() 将 重新调整数组的维数。  

```py
# np.arange()
arr = np.arange(15) # 15个元素的 一维数组
print(arr)
print(arr.reshape(3, 5)) # 3x5个元素的 二维数组
print(arr.reshape(1, 3, 5)) # 1x3x5个元素的 三维数组
```

np.arange() 和 random.shuffle():random.shuffle() 将打乱数组序列（类似于洗牌）。   

```py
arr = np.arange(15)
print(arr)

np.random.shuffle(arr)
print(arr)
print(arr.reshape(3,5))
```

#### 2.4 ndarray的数据类型

dtype参数：指定数组的数据类型，类型名+位数，如float64, int32  

astype方法：转换数组的数据类型  

```py
# 初始化3行4列数组，数据类型为float64
zeros_float_arr = np.zeros((3, 4), dtype=np.float64)
print(zeros_float_arr)
print(zeros_float_arr.dtype)

# astype转换数据类型，将已有的数组的数据类型转换为int32
zeros_int_arr = zeros_float_arr.astype(np.int32)
print(zeros_int_arr)
print(zeros_int_arr.dtype)
```



