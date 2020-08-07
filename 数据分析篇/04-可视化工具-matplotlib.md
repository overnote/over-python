## 一 matplotlib简介

matplotlib模仿Matlab构建，是当前最流行的Python底层绘图库，主要用来制作可视化的数据图标。  

安装：
```
conda install matplotlib
```

入门程序：
```py
from matplotlib import pyplot as plt

# x轴数据，是一个可迭代对象
x = range(2, 26, 2)         # x轴从2开始，每次增加2，最大值为26

# y轴数据，是一个可迭代对象，绘制的结果是 (2,15),(4,13),(6,14.5)....(24,15)
y = [15, 13, 14.5, 17, 20, 25, 26, 26, 24, 22, 18, 15]

plt.plot(x, y)
plt.show()
```

运行结果：  
![](../images/python/aa-02.png)  


## 二 matplotlib 简单使用

#### 2.1 设置生成图片

```py
from matplotlib import pyplot as plt

fig = plt.figure(figsize=(20, 8), dpi=80)

x = range(2, 26, 2)
y = [15, 13, 14.5, 17, 20, 25, 26, 26, 24, 22, 18, 15]

plt.plot(x, y)
plt.savefig("./demo.svg")
plt.show()
```

#### 2.2 常用设置

设置X轴刻度：
```py
plt.xticks(x)           # 当刻度太密集可以使用列表步长（间隔取值）来解决 plt.xticks(x[::2]) 
```




