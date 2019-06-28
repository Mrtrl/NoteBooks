## DeepHash启动

### 准备工作

```shell
# 将./DeepHash目录添加到环境变量当中
>>>(DeepHash) kong@Test:~$
>>>(DeepHash) kong@Test:~$ export PYTHONPATH=./DeepHash/DeepHash:$PYTHONPATH
>>>(DeepHash) kong@Test:~$ source .bashrc
```

### 启动项目

```shell
>>>(DeepHash) kong@Test:~$ (DeepHash) kong@Test:~$ cd DeepHash/examples/dch/
>>>(DeepHash) kong@Test:~/DeepHash/examples/dch$ python train_val_script.py --gpus "0,1" --data-dir $PWD/../../data
```

