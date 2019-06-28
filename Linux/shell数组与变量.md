## 简单教程

### 创建shell脚本文件

首先创建一个test.sh文件，并在文件里写入一下句式

`echo "Hello World!!"`

### 运行shell脚本文件（启动）

1. 作为可执行程序

```shell
chmod +x ./test.sh  # 使脚本具有执行权限
./test.sh  # 执行脚本
```

2. 作为解释器参数

```shell
/bin/sh test.sh
/bin/php test.php  # 如果使用php作为解释器的话 
```

### shell变量

```shell
# 定义变量时，变量名不加美元符号($, PHP语言中变量需要), 如：
your_name = "runoob.com"
```

- 有效的Shell变量名示例如下：

```shell
RUNOOB
LD_LIBRARY_PATH
_var
var2
```

- 无效的变量名

```shell
?var = 123
user*name =  runoob
```

- 除了显式的直接赋值，还可以用语句给变量赋值，如：

```shell
for file in 'ls/etc'
或
for file in $(ls/etc)
```

### 使用变量

使用一个定义过的变量，只要再变量名前面加美元符号即可，如：

```shell
your_name = "qinjx"
echo $your_name
echo ${your_name}
```

变量名外面的花括号是可选的，加不加都行，加花括号是为了帮助解释器识别变量的边界，比如下面的这种情况：

```shell
for skill in Ada Coffe Action Java; do
	echo "I am good at ${skill}Script"
done
```

如果不给skill变量加花括号，写成echo "I am good at $skillScript"，解释器就会吧$skillScript当成一个变量（其值为空）

已定义的变量，可以被重新定义，如：

```shell
your_name = "tom"
echo $your_name
your_name = "alibaba"
echo $your_name
```

### 只读变量

使用readonly 命令可以将变量定义为只读变量，只读变量的值不能被改变。

下面的例子尝试更改只读变量，结果报错：

```shell
# !/bin/bash
myUrl = 'http://www.google.com'
readOnly myUrl
myUrl = 'http://www.runoob.com'
```

### 删除变量

使用`unset`命令可以删除变量。语法：

```shell
unset variable_name
```

**实例**

```shell
#!/bin/sh
myUrl = "http://www.runoob.com"
unset myUrl
echo myUrl
```

### 变量类型

运行shell时，会同时存在三种变量：

- 局部变量 局部变量在脚本或命令中定义，仅在当前shell实例中有效，其他shell启动的程序不能访问局部变量
- 环境变量 所有的程序，包括shell启动的程序，都能访问环境变量，有些程序需要环境变量来保证其正常运行。必要的时候shell脚本也可以定义环境变量。
- shell变量 shell变量是由shell程序设置的特殊变量。shell变量中有一部分是环境变量，有一部分是局部变量，这些变量保证了shell的正常运行

### Shell字符串

字符串是shell编程中最常用最有用的数据类型（除了数字和字符串，也没啥其他类型好用了），字符串可以用单引号，也可以用双引号，也可以不用引号。单双引号的区别跟php类似。

- 单引号

```shell
str='this is a string'
```

单引号字符串的限制：

- 单引号里的任何字符串都会原样输出，单引号字符串中的变量是无效的
- 单引号字符串中不能出现单独一个的单引号(对单引号使用转义符后也不行)，但可成对出现，作为字符串拼接使用

- 双引号

```shell
your_name = "runoob"
str = "Hello, I know you are \"$your_name"! \n"
```

双引号的优点：

- 双引号里可以有变量
- 双引号里可以出现转移字符

### 拼接字符串

```shell
your_name = "runoob"
# 使用双引号拼接
greeting = "hello, "$your_name"!"
greeting_1 = "hello, ${your_name}!"
# 使用单引号拼接
greeting_2 = 'hello, '$your_name' !'
greeting_3 = 'hello,  ${your_name} !'
echo $greeting_2 $greeting_3
```

输出结果为：

```
hello, runoob ! hello, runoob !
hello, runoob ! hello, ${your_name} !
```

**总结：**双引号可以使用变量拼接字符串，单引号可以使用成对的`''`单引号来拼接字符串

### 获取字符串长度

```shell
string = 'abcd'
echo ${#string} # 输出4
```

### 提取子字符串

```shell
string = "runoob is a greate site"
echo ${string:1:4} # 输出unoo
```

### 查找子字符串

查找字符`i`或`o`的位置(哪个字母先出现就算哪个)

```shell
string = "runoob is a greate site"
echo = `expr index "$string" io` # 输出 4
```

注意：** 以上脚本中 ` 是反引号，而不是 ' 单引号，不要看错了吖

## Shell数组

### 定义数组

在Shell 中，用括号来表示数组，数组元素用”空格“分割开。定义数组的一般形式为：

```shell
数组名=（值1 值2 ...值n）
```

例如：

```shell
array_name = (value0 value1 value2 value3)
```

或者

```shell
array_name = (
	value0
	value1
	value2
	value3
)
```

### 获取数组中的元素

```shell
array_name[0]=value0
array_name[1]=value1
array_name[2]=value2

# 读取数组中的元素
${array_name[index]}
echo "第一个元素：${my_array[0]}"

# 获取所有元素可以用 @ 或者 *
${array_name[*]}
echo "第一个元素：${my_array[*]}"
```

### 获取数组的长度

```shell
echo "数组元素个数为：${#my_array[*]}"
```

