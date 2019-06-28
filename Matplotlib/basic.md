## MatplotLib 基础学习

### 简介

matplotlib是python的一个绘图工具包。它是基于matlib开发的第三方库，所以也能像matlib一样绘制出种类丰富的图形

### 进入python环境

**注：以下开发环境基于Notebook**

1. 进入环境

```python
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd

# 设置直接在notebook中输出徒刑
%matplotlib inline
# 设置图形的清晰度
%config InlineBackend.figure_format = 'retina'
```

2. 绘制余弦图

```python
# 先设置坐标X的取值范围，定义余弦函数
x = np.arange(0, 15, 0.1)
y = np.cos(x)
# 开始绘图
plt.plot(x, y)
```

3. 优化

```python
# 将前面的函数搬下来
x = np.arange(2, 15, 0.1)
y = np.cos(x)
plt.plot(x, y)
# 添加标题，X轴和轴的名称
plt.title('cos function')
plt.xlabel('x value')
plt.ylabel('y value')
# 展示画出的图像
plt.show()
```

### Subplot

Subplot相当于子图的意思，就是在一块画布中存在多张图表

