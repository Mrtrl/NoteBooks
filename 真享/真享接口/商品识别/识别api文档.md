## 相似商品识别

### /outside/similarity/<path:category>

```python
# 调用地址
url = 'http://47.101.192.138:8888/outside/similarity/<path:category>'
category = ['bag', 'clothe', 'shoe'] # 这些都是可选的，后面可以分开

# 调用方式 --> POST

# 调用格式
{
    'image_url': 'https://api.realshare.com/xxxx.jpg'
}

# 返回格式
      
{
    "status":200,
    "img_id":"24280abc4e517245e0430528a4549d9d",
    "total":20,
    "data":[
        {
            "website":"burberry",
            "category":[
                "Bags",
                "All Bags Tmp 2"
            ],
            "description":[
                "A block-colour bucket bag sculpted and lined in supple calf leather. The sleek style is topped with a military-inspired belt strap and comes with a removable calf leather pouch."
            ],
            "img":"00002_burberry_40732801_582.jpg",
            "title":"The Small Leather Bucket Bag",
            "brand":"burberry",
            "product_id":"40732801",
            "accuracy":"0.7356086",
            "price":"13900.0",
            "size":[
                "Small",
            ]
        },
    ]
}
```

### /inner/similarity/<path:category>

```python
# 调用地址

# 返回格式
{
    'status': 200,
    'msg': 'success',
    'count': type(int),
    'result': [
        {'pid': xxxxx, score: xxxx}
    ]
}
```

### tag_img

```python
# 调用地址

```

#### 图片接口Restful风格化

```python
# 根目录
$inner or $outside  (数据来源分为，内部和外部)
# 一级子目录
$similarity
# 二级子目录
$bag
# 三级子目录
$handbag 
```

### 图片逻辑处理

#### 上传

```python

```

#### 识别

```python

```

#### 报错

```python

```

