## 错误

### dash --> bash兼容问题

```shell
Syntax error: "(" unexpected
```

代码没问题的情况下一直出现这种报错，就是指执行sh文件时 系统默认使用了`dash`而非`bash`，运行下面代码就可以检测系统得默认sh

```shell
>>> ll /bin/sh
>>> lrwxrwxrwx 1 root root 4 Mar 26  2018 /bin/sh -> dash*
```

如果结果为上则可以改用以下命令执行`sh`文件

```shell
# 编译器形式
/bin/bash test.sh 

# 可执行程序形式
chmod +x ./test.sh
./test.sh # 注： "."不能省略
```

