## Rs-det项目简介

### 简介

Rs-det主要有三个Ai视觉模块组成，可以实现主体识别+相似图像检索的功能
，并且给予flask服务器提供外部Api.

#### 项目结构

```mermaid

```

#### 环境依赖

``` python
tensorflow == 1.9.0
python == 2.7.0
```

#### 服务器所在位置

`IP: 47.52.101.138`

#### Api返回结构

```python
# 正确
{
    'sucess': {
        'count': type(int)
        'result': {[img_dict], [...], [..]}
    }
}

# 错误
{
    'error': 'error reason.....'
}
```

#### Api请求结构

```python
# 图片识别 -- ajax请求

{
    
}
```

### 接口列表

#### retri_Img

`这是一个查找外部相似图片的接口`

```python
# 请求
# 要求一张jpg格式的图片

# 返回
{
    'sucess': {
        'count': type(int)
        'result': [{product_img_dict},{....}]
    }
}
```

#### retri_Inner

`这是一个查找内不相似图片的接口`

```python
# 请求
# 要求一张jpg格式的图片

# 返回
{
    'sucess': {
        'count': type(int)
        'result': [(pid, score), (...),.....]
    }
}
```

#### tag_Img

`这是一个对图片进行标记的接口`

```python
# 请求 
{
	'pixId':,
    'picName':,
    'tag':[{},{}],
}

# 返回
{
    'sucees': 200
}

{
    'error': reason -> type(str)
}
```

