## Caffe

### 简介

- caffe由伯克利贾扬清开发，facebook开源，使用C++语言开发-

- 比较适合用在CNN网络开发（物体检测相关）
- caffe比较多的命令行操作（shell）

### 版本

- Caffe-cpu
- Caffe-cuda

### 安装

##### 下载caffe安装包

`git clone xxxxxx`

##### 编译文件

```shel
cd caffe

# 查看配置文件
vim Makefile.config

# 开始编译 -- 需要提前安装make工具包
make all -j32  # j32代表可以进行并发编译

# 查看tools
cd tools
ls 
./exreact_features # 提取特征
....
```

####下载数据包

```shell
$curl XXXXX 
```

####测试

``` shell
# 网络 Lenet

# 数据集 cifar10k
bash xxxxx

# 加载训练脚本
./examples/mnist/train_lenet_adam.sh

# 
```

### 存储

caffe主要使用LMDB数据库实现数据集的读取（高效IO）

```python
# 存储

```

#### 网络结构定义

```shell
# 使用google proto buf定义网络的结构

```



#### 特征提取

```shell
./build/tools/extract_features.bin
```

#### 训练



#### 模型保存





#### 问题

```shell
1. LMDB是什么？
2. caffe的命令
3. 
```





#### 1.基本环境设定

- 可视化工具库

```python
from pylab import *
%matplotlib inline
```

- 配置环境路径，导入`caffe`库

```python
caffe_root = '/opt/caffe'
import sys
sys.path.insert(0, caffe_root + 'python')
import caffe
```

- 下载与准备数据

```python
import os
os.chdir(caffe_root)
# Download data
!data/mnist/get_mnist.sh
# Prepare data
!examples/mnist/create_mnist.sh
# back to examples
os.chdir('examples')
```

Downloading...

Creating lmdb...

#### 2. 创建网络

```python
from caffe import layers as L, params as p

def lenet(lmdb, batch_size):
  	pass
  
```

