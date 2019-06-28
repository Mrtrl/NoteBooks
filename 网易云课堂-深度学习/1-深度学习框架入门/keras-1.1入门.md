## Keras快速上手

### 1.1 引入库，初始化模型架构

```python
from keras.models import Sqquential
model = Sequential()
```

### 1.2 通过add来添加层

我们举一个最简单的MLP例子，这下面我们添加的都是全连接层

```python
from keras.layers import Dense, Activation

model.add(Dense(units=64, input_dim=100))  # 100维的数据
model.add(Activattion("relu"))
model.add(Dense(units=10))
model.add(Activation("softmax"))
```

### 1.3 通过compile来编译模型

```python
model.compile(loss="categorical_crossentropy", optimizer="sgd", metrics=['accuracy'])
```

编译模型时必须指明损失函数和优化器，如果你需要的话，也可以自己定制损失函数。Keras里也封装好了很多优化器和损失函数。

```python
from keras.optimizers import SGD
model.compile(loss='categorical_crossentrogy', optimizer=SGD(lr=0.01, momentum=0.9, nesterov=True))
```

### 1.4 把数据灌进来训练

```python
# 示例
model.fit(x_train, y_train, epochs=5, batch_size=32)
```

你也可以选择，手动一批一批数据训练，大概就是下面这个样子

```python
# 示例
model.train_on_batch(x_batch, y_batch)
```

### 1.5在测试集上评估效果

```python
# 示例
loss_and_metrics = model.evaluate(x_test, y_test, batvh_size=128)
```

### 1.6 实际预测

```python
classes = model.predict(x_test, batch_size=128)
```

