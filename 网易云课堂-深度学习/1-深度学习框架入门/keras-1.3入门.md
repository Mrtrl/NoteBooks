## Keras fine-tuning

### 利用Keras进行模型微调

```python
# 首先选择一个合适的cnn模型--例如：Vgg16
from keras.applications import VGG16

# 获取预训练模型--例如：imagenet，和对应的处理工具
from keras.applications.imagenet_utils import preprocess_input, decode_predictions

# 使用tensorflow做为keras的底层支撑
import tensorflow as tf
from keras.backend.tensorflow_backend import session
# 使用ConfigProto对框架运行进行设定（例如分配显存）-- tensorflow底层使用Protocol作为文件设置格式
config = tf.ConfigProto() # 创建ConfigProto对象
config.gpu_options.perprocess_gpu_memory_fraction = 0.3
set_session(tf.Session(config=config)
```

### 下载预训练模型，并且拷贝到指定目录

```python
!mkdir -p ~/.keras/models
!cp /data/Deep_learning/vgg16_weights_tf_dim_ordering_tf_kernels.h5 ~/.keras/models/vgg16_weights_tf_dim_ordering_tf_kernels.h5
```

```python
vgg16 = VGG16(include_top=True, weights='imagenet' ) # 是否保留1000分类的softmax层
vgg16.summary() # 展示（打印）模型的结构
```

### 使用预训练模型预估

```python
IMAGENET_FOLDER = 'img/imagenet'
!ls img/imagenet
```

```python
!wget https://raw.githubusercontent.com/raghakot/keras-vis/master/resources/imagenet_class_index.json
!mv imagenet_class_index.json ~/.keras/models/

from keras.preprocessing import image  # 图片操作
import numpy as np

img_path = os.path.join(IMAGENET_FOLDER, 'strawberry_1157.jpg')
img = image.load_img(img_path, target_size=(224, 224))
x = img.img_to_array(img)
x = np.expand_dims(x, axis=0)
x = preprocess_input(x)
print('Input image shape:', x.shape)

preds = vgg16.predict(x)
print('Predicted:', decode_predictions(preds))
```

```python
img_path = os.path.join(IMAGENET_FOLDER, 'apricot_696.jpeg')
img = image.load_img(img_path, target_size=(224, 224))
x = image_to_array(img)
x = np.expand_dims(x, axis=0)
x = preprocessing_input(x)
print('Input image shape:', x.shape)

preds = vgg16.predict(x)
print('Predicted:', decode_predictions(preds))
```

**总结：**以上步骤，实现了通过keras中的使用imagenet训练的vgg16模型进行预测，接下来的步骤就是进行各预测层的可视化









