## priceMoniter

### 简介

此项目主要用作追固定几个网站的商品加个和库存波动

### 结构

```python
{
    'product_id': 'xxxxxxxx',
    'quantity':[
        's': '4',
        'xs': '5', # 避免写入格式错误的发生，统一将数量和价格都设置成string格式
    ]，
    'price':{
        'size': 'price',
        'default': 'price',
    }
}
```

