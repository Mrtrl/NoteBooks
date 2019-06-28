## Pickle序列化模型

### 加载

```python
# encoding:utf-8
import pickle

temp_list = [
    [1,2,3],
    [4,5,6]
]

temp_dict = {
    0:[1, 2, 3, 4],
    1: 'string',
    2: {'key': 'value'},
}
```

### 序列化写入和保存

```python
# 使用dump()将数据序列化到文件中
fw = open('dataFile.txt', 'wb')
# Pickle the list using the highest protocol available
pickle.dump(temp_list, fw, -1) # -1?
# Pickle dictionary using protocol
pickle.dump(temp_dict, fw)
fw.close()
```

### 序列化读取

```python
fr = open('dataFile.txt', 'rb')
data_list = pickle.load(fr)
print(data_list)

data_dict = pickle.load(fr)
print(data_dict)
fr.close()
```

### pickle格式存入 -- 使用protocol协议

```python
test_dict =  {'a': 'abc'}

# 保存
with open('data.pickle', 'wb') as f:
    pickle.dump(test_dict,f , protocol=pickle.HIGHEST_PROTOCOL)
# 读取
with open('data.pickle', 'rb') as f:
    test_dict = pickle.load(f)
```

### 总结

按顺序写，按顺序读

