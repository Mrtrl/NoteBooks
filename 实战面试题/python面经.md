#  Python面试基础题目大全（3）

![img](https://ci.xiaohongshu.com/xy_emo_deyi.png?v=2) 8、请至少列举5个 PEP8 规范

（1）、缩进：每一级4个缩进。连续跨行应该使用圆括号或大括号或者使用悬挂缩进。

（2）、代码长度约束

一行列数：PEP8 规定最大为79列，如果拼接url很容易超限

一个函数：不可以超过30行；直观来讲就是完整显示一个函数一个屏幕就够了，不需要上下拖动

一个类：不要超过200行代码，不要超过10个方法

一个模块：不要超过500行

（3）、import

不要在一句import中引用多个库

（4）、命名规范

（5）、注释

总体原则，错误的注释不如没有注释。所以当一段代码发生变化时，第一件事就是要修改注释！

![img](https://ci.xiaohongshu.com/xy_emo_deyi.png?v=2) 9、通过代码实现如下转换：

答案： 二进制转换成十进制：v = “0b1111011”

print(int('0b1111011',2))

十进制转换成二进制：v = 18

print(bin(18))

八进制转换成十进制：v = “011”

print(int('011',8))

十进制转换成八进制：v = 30

print(oct(30))

十六进制转换成十进制：v = “0x12”

print(int('0x12',16))

十进制转换成十六进制：v = 87

print(hex(87))

![img](https://ci.xiaohongshu.com/xy_emo_deyi.png?v=2) 10、请编写一个函数实现将IP地址转换成一个整数。

如 10.3.9.12 转换规则为：

10 00001010

3 00000011

9 00001001

12 00001100

再将以上二进制拼接起来计算十进制结果：00001010 00000011 00001001 00001100 = ？

答案：

def func(x):

lis = x.strip().split('.')

li = [bin(int(i)) for i in lis]

li2 = [i.replace('0b',(10-len(i))*'0') for i in li]

return int(''.join(li2),2)

ret = func('10.3.9.12')

print(ret)

Python![img](https://ci.xiaohongshu.com/xy_emo_r_daxiao.png?v=2) study![img](https://ci.xiaohongshu.com/xy_emo_r_xieyan.png?v=2) q.u.n

⑦⑧④⑦⑤⑧②①④



#### http://www.matools.com/blog/190553373

#### http://www.mamicode.com/info-detail-2405140.html

