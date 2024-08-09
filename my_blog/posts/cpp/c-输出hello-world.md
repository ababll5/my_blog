---
title: c++输出hello world
date: 2024-06-21 10:08:50
cover: http://ababll5.asia/vip/2024/07/22/669d3a656a227.jpg
tags:
   cpp
---

# c++输出hello world教程

### 首先得有头文件
```c++
#include<iostream>
```
### 然后主函数
```C++
int main(void)
```
### 全代码
```c++
#include<iostream>
int main(void)
{
    std::cout<<"hello world"<<std::endl;     //endl是换行的意思(注意：写完记得加分号;)
    return 0;                           //程序结束
}
```
如果编译成exe发现打开后窗口一闪而过怎么办呢？  
## 如果是Windows用户那就在`return 0;`的上面加一个  
```c++
sysytem("pause")              //这个代码的意思就是用Windows的终端命令pause(按任意建继续)
```

## 如果是Linux用户那就在`return 0;`的上面加个
```c++
cin.get();                   //不管什么用户都最好用这个，这行代码所有系统都能运行
```
