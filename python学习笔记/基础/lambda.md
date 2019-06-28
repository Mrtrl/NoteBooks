## Lambda

### 简介

Lambda是Python内置的匿名函数，使用者可以用简洁的代码实现一个简单的函数，不用重新进行命名。

### 在排序中的应用

```python
# lambda sort，按照列表元素的长度进行排序
temp_list = ['ab', 'a', 'abcd', 'xxxxxx']
temp_list.sort(key=lambda x:len(x))
------------------------------
# temp_list ['a', 'ab', 'abcd', 'xxxxxx']
```

