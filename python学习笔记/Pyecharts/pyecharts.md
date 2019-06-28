## Pyecharts模块

## 安装

```shell
# 安装 1.0.x 以上版本
$ pip install pyecharts -U

# 如果需要安装 0.5.11版本的开发者，可以使用
$ pip install pyecharts==0.5.11
```

### 本地环境

### 生成HTML -- python 3.6+

```python
from pyecharts.charts import Bar
from pyecharts import options as opts

bar = (
	Bar()
    .add_xaxis(['衬衫', '毛衣', '领带', '裤子', '风衣', '高跟鞋', '袜子'])
    .add_yaxis(['商家A'], [114, 55, 27, 101, 125, 27, 105])
    .add_yaxis(['商家B'], [57, 134, 137, 129, 145, 60, 49])
    .set_global_opts(title_opts=opts.TitleOpts(title='某商场销售情况'))
)
bar.render()
```

