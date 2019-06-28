## Jupyter Notebook基本操作

### 简介

JupyterNotebook是一个专门用来进行数据科学研究的工具，这篇笔记主要介绍一些Jupyter Notebook简单操作

### 工具栏

![img](http://pic1.tsingdataedu.com/%E5%B7%A5%E5%85%B7%E6%A0%8F.png)

```shell
## 操作练习： 增加一行
## 操作练习： 把cell剪切走
## 操作练习： 把cell复制，并粘贴在下方....
## 操作练习： 把cell移动到上方...
```

### 熟悉快捷键操作

  - **b**：在当前行下面插入新的cell*（命令模式）*
  - **a**：在当前行上面插入新的cell*（命令模式）*
  - **dd **(敲击d键两下)：删除当前cell*（命令模式）*
  - **z**：撤销对某个cell的删除*（命令模式）*
  - **m**: markdown模式

```shell
# 1.敲击b键，在我下面增加一行
# 2.敲击a键，在我上面增加一行
# 3.双击d键，删除我这行
# 4.敲击Z键，撤销删除
# 敲击m键，把note转换成markdown
```

#### matplotlib

```python
# 操作练习：为当前的cell加入line number: 单L(命令模式)
%matplotlib inline
import numpy as np
import matplotlib as mpl
import matplotlib.pyplot as plt
np.random.seed(sum(map(ord, "aesthetics"))) # 给每一个任务单独分配随机种子
def sinplot(flip=1):
  x = np.linspace(0, 14, 100)
  for i in range(1, 7):
    plt.plot(x, np.sin(x + i * .5) * (7 - i) * flip)
sinplot()
```

