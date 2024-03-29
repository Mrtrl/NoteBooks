## Markdown

### 简介

Markdown是一种很方便的记录工具，通过固定命令和丰富的插件，使用者只需要掌握少数几个命令就能写出简洁明了结构工整的文章，使用者不需要像使用word一样调整像是行间距、缩进等等复杂的格式

### 使用

#### 标题

```shell
# h1
## h2
### h3
```

#### 字体

```shell
**文字加粗**
*斜体*
***加粗斜体***
~~这是加删除线的文字~~
```

#### 引用

```shell
> 这是引用的内容
>> 这也是引用
>>>> 这仍然是引用
```

效果如下

> 这是引用的内容
> > 这也是引用
> >
> > >> 这仍然是引用

#### 分割线

```shell
---
----
***
*****
```

效果如下:

---
----
***
*****

#### 图片

```shell
![图片alt](图片地址 ''图片title'')

```

#### 超链接

```shell
[title](url)
```

示例：

[title](https://www.baidu.com)

#### 代码结构

```shell
​```  <- 像左边一样 3个 "`"呼出代码块
```

#### 列表

- 无序列表

```shell
- 列表内容
+ 列表内容
* 列表内容

注意： - + * 跟内容之间都需要有个间隔
```

示例

- -号

+ +号

* *号



- 有序列表

数字加点

```shell
1. 列表内容
2. 列表内容
3. 列表内容
```

示例：

1. 列表内容
2. 列表内容
3. 列表内容



- 列表嵌套

- 无序内容
  - 二级无序内容
  - 二级无序内容

#### 表格

```shell
表头|表头|表头
---|:--:|---:
内容|内容|内容
内容|内容|内容

第二行分割表头和内容
- 有一个就行位了对齐，多加了几个
-两边加：表示文字居中
-右边加：表示文字居右
注：原生的语法两边都要用 | 包起来。此处省略
```

示例：

```shell
姓名|技能|排行
--|:--:|--:
刘备|哭|大哥
关羽|打|二哥
张飞|骂|三弟
```

效果：

| 姓名 | 技能 | 排行 |
| ---- | :--: | ---: |
| 刘备 |  哭  | 大哥 |
| 关羽 |  打  | 二哥 |
| 张飞 |  骂  | 三弟 |

#### 流程图

~~~flow
```flow
st=>start: 开始
op=>operation: My Operation
cond=>condition: Yes or No?
e=>end
st->op->cond
cond(yes)->e
cond(no)->op
```
~~~

