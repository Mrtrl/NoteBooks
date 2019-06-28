## data_provider

### 简介

从标准数据集中获取训练数据

### 代码解读

```python
class Dataset(object):
    
    def __init__(self, modal, data_root, path, train=True):
        self.lines = (训练文件列表)
        self.data_root = (训练数据根目录)
        self.n_samples = (文件数)
        self.train = (是否训练 True/False)
        asser modal == 'img' # 判断是否为图片数据集
        self.modal = 'img'
        self._img = [0] * self.n_samples  # 创建矩阵（但是写法不规范）
        self._label = [0] * self.n_samples  
        self._load = [0] * self.n_samples
        self._status = 0  
        self.data = self.img_data  # 读取加载图片
        self.all_data = self.img_all_data  # 整个数据集
        
    def get_img()
    	path = os.path.join(self.data_root, self.inlines[i].strip().split()[0])  # 拼接文件路径
        return cv2.resize(cv2.imread(path), (256， 256))
    
    def get_label(self, indexes):
        return [int(j) for j in self.lines[i].strip().split()[1:]]
    
    def img_data(self, i):
        if self._status:
            # 同步加载所有照片和对应的标签
            return (self._img[indexes, :], self.label[indexes, :])
        else:
            ret_img = []
            ret_label = []
            try:
                 if self.train:
                        if not self._load[i]:
                            self._img[i] = self.get_img(i)
                            self._label[i] = self.get_label(i)
                            self._load[i] = 1
                            self._load_num += 1
                        ret_img.append(self._img[i])
                        ret_label.append(self._label[i])
                  else:
                        self._label[i] = self.get_label(i)
                        ret_img.append(self.get_img(i))
                        ret_label.append(self._label[i])
                except Exception as e:
                    print('cannot open {}, exception: {}'.format(self.lines[i].strip(), e))
               
               # 读取完毕，修改状态
               if self._load_num == self.n_samples:
                    self._status = 1
                    self._img = np.asarray(self._img)
                    self._label = np.asarray(self._label)
            	return (np.asarray(ret_img), np.asarray(ret_label))
            
            def img_all_data(self):
                if slef._status:
                    return (self._img, self._label)
                
            def get_labels(self):
                for i in range(self.n_samples):
                    if self._label[i] is not list:
                        self._label[i] = [
                            int(j) for j in self.lines[i].strip().split()[1:]
                        ]
	
    def import_train(data_root, img_tr):
        '''
        # 返回训练数据集
        return (img_tr, txt_tr)
        '''
    	return (Dataset('img', data_root, img_tr, train=True))
    
    def import_validation(data_root, img_te, img_db):
        '''
        # 返回验证数据集
        return (img_te, txt_te, img_db, txt_db)
        '''
        return (Dataset('img', data_root, img_te, train=False),
               Dataset('img', data_root, img_db, train=False)
               )
    
```

