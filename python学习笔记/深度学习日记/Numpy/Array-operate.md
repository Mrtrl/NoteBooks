## Array -- 数组操作

### 简介

要了解如何使用Numpy就需要了解Array，因为Numpy的主要作用就是操作数组(Array)

#### 创建 Numpy Array

```python
import Numpy as np
Test_Array = np.array([[1,2,3],[4,5,6]])
```

#### Array的形状 -- shape

```python
print(Test_Array.shape)
------------------- 输出的是一个2*3数组
(2,3)
```

#### Array的维度 -- ndim

```python
print(Test_Array.ndim)
------------------ 输出的是一个数字
2
```

#### 翻转 Array

```python

```

#### 数组相减 subtract

```shell
>>> np.subtract(1.0, 4.0)  # 简单相减
-3.0

>>> x1 = np.arange(9.0).reshape((3,3)) # 生成3*3数组
array([[0., 1., 2.],
       [3., 4., 5.],
       [6., 7., 8.]])

>>> x2 = np.arange(3.0).reshape(3.0) # 生成一维数组
array([0., 1., 2.])

>>> np.subtract(x1, x2) # 数组相减
array([[0., 0., 0.],
       [3., 3., 3.],
       [6., 6., 6.]])
```

#### 生成对角矩阵 eye

```shell
>>> np.eye(2)
array([[1., 0.],
       [0., 1.]])
```

#### 矩阵均值

```python
a = np.array([1,2,3], [4,5,6])
mean = np.mean(a, axis=0)
```



#### 范数 Linalg.norm

[参考文章](https://blog.csdn.net/bitcarmanlee/article/details/51945271)

``` python

```





