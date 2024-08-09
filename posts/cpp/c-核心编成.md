---
title: 内存分区模型
date: 2024-07-01 18:27:21
cover: https://img.picui.cn/free/2024/06/27/667ce46c313f4.png
tags:
   cpp
---



# 前言

从做完那个“通讯录管理系统”起我已经不再是一个初学c++的小白了，我现在的c++已经入门了,以后我会放进阶的教程到我的博客，源码也都会放在[我的github](https://github.com/ababll5/blog_cpp)  上欢迎大家学习



# c++核心编程

本阶段主要正对c++**面向对象**的编程技术做详细讲解，探讨c++中核心和精髓



## 内存分区模型

c++程序执行是，将内存大方向划分为4个区

- 代码区：存放函数体的二进制代码，由操作系统进行管理
- 全局区：存放全局变量和静态变量以及常量
- 栈区：由编译器自动分配释放，存放函数的参数值，局部变量等
- 堆区：由程序员分配和释放，若程序员不释放，程序结束时由操作系统回收



内存四区意义：

不同区域存放的数据赋予不同的生命周期，给我们更大的灵活编成



### 程序运行前

在程序编译后，生成了exe可执行程序，未执行程序前分为两个区域

代码区：

存放cpu执行的机器指令 

​    代码区是共享的，共享的目的是对于频繁执行的程序，只需要在内存中有一份大麻即可

​    代码去是只读的，使其只读的原因是防止程序意外地修改了他的指令



全局区：

​    全局变量和静态变量存放在此

​    全局区还包含了常量区，字符串常量

   该区域的数据在程序结束后由操作系统释放



演示区：

```cpp
#include <iostream>
using namespace std;

// 全局变量
int g_a = 10;
int g_b = 10;

// const 修饰全局变量
const int c_g_a = 10;
const int c_g_b = 10;

int main(void)
{
    // 全局区

    // 全局变量、静态变量、常量

    // 创建普通的局部变量
    int a = 10; // 普通的局部变量
    int b = 10;

    cout << "局部变量a的地址为: " << (long long)&a << endl;
    cout << "局部变量b的地址为: " << (long long)&b << endl
         << endl;

    cout << "全局变量g_a的地址为: " << (long long)&g_a << endl;
    cout << "全局变量g_b的地址为: " << (long long)&g_b << endl
         << endl;

    // 静态变量
    static int s_a = 10;
    static int s_b = 10;

    cout << "镜头变量s_a的地址为: " << (long long)&s_a << endl;
    cout << "静态变量s_b的地址为: " << (long long)&s_b << endl
         << endl;

    // 常量
    // 字符串常量
    cout << "字符串常量的地址为： " << (long long)&"hello world" << endl
         << endl;

    // const修饰的变量

    // const修饰全局变量  const 修饰局部变量
    cout << "全局常量c_g_a的地址为: " << (long long)&c_g_a << endl;
    cout << "全局常量c_g_b的地址为: " << (long long)&c_g_b << endl<<endl;

    // const 修饰局部变量
    const int c_l_a = 10;
    const int c_l_b = 10;

    cout << "局部常量c_l_a的地址为: " << (long long)&c_l_a << endl;
    cout << "局部常量c_l_b的地址为: " << (long long)&c_l_b << endl;

    return 0;
}
```



输出结果:

![](https://img.picui.cn/free/2024/07/02/66841d6729bab.png)



#### 总结

记住红色区的就好了

![](https://img.picui.cn/free/2024/07/02/66841dfe87802.png)

总结：

- c++在程序运行前风味全局区和代码区
- 代码区的特点就是共享和只读
- 全局区中存放变量、静态变量‘常量
- 常量区中存放const修饰的全局常量和字符常量



## 程序运行后

栈区：

​     由编译器自动分配内存，存放函数的参数值，局部变量等

​     注意事项：不要返沪局部变量的地址，栈区开辟的数据由编译器自动释放

示例：

```cpp
#include <iostream>
using namespace std;

// 栈去注意事项  --- 不要返回局部变量的地址
// 战区数据由编译器管理开辟和释放

int* func(int b) //形参数据也会放在栈区
{
    b = 100;
    int a = 10; // 局部变量 存放在栈区，栈区的数据在函数执行完后自动释放
    return &a;  // 返回局部变量地址
}

int main(void)
{
    int b;
    int* p = func(1);

    cout << *p << endl; //在x86下第一次可以正常打印
    cout << *p << endl; //在x86下第二次就不可以
    
    system("pause");
    return 0;
}
```

自行体会吧



堆区：

​     由程序员分配释放若程序员不释放，程序结束时由操作系统回收

​     在c++主要利用new在堆区开辟内存

示例：

```cpp
#include<iostream>
using namespace std;

int * func()
{
	//利用new关键字，可以将数据开辟到堆区
	//指针本质也是局部变量，放在栈上，指针的保存在堆区
	int * p = new int(10);

	return p;
}

int main(void)
{
	//在堆区开辟数据
	int * p = func();

	cout << *p << endl;

	system("pause");
	return 0;
}
```

总结：

   堆区数据又程序员管理开辟和释放

   堆区数据利用new关键字进行开辟内存



## new操作符

c++中利用new操作符再堆区开辟数据

堆区开辟的数据，由程序员手动开辟手动释放，释放利用操作符delete

语法: ` new 数据类型`

利用new创建的数据，会返回该数据对应的类型指针



不过在写代码前我们得先创建一个堆区

```cpp
int *func()
{
    // 在读取创建整型的数据
    // new 返回时该数据的内型指针
    int * p = new int(10);
    return p;
}
```







示例1：基本语法

```cpp
void test01()
{
  int * p = func();
  cout << *p << endl;
  cout << *p << endl;
  cout << *p << endl;
  cout << *p << endl;
  //堆区的数据 由程序员管理开辟，程序员管理释放
  //如果想释放堆区的数据，利用关键字delete
  delete p;
  //cout<<*p<<endl;  由于已经delete释放了再次访问会报错
}
```



示例2：开辟数组

```cpp
// 2 在堆区利用new开辟数组
void test02()
{
    //创建10个整形数据的数组，在堆区
    int * arr = new int[10];
    
    for (int i = 0; i < 10; i++)
    {
        arr[i] = i + 100;//给10个元素复制 100 ~ 109
    }

    for (int i = 0; i < 10; i++)
    {
        cout << arr[i] << endl;
    }
    
    //释放
    //释放数组要加[]
    delete[] arr;
}
```



全部：

```cpp
#include <iostream>
using namespace std;

// 1 new的基本语法
int *func()
{
    // 在读取创建整型的数据
    // new 返回时该数据的内型指针
    int * p = new int(10);
    return p;
}

void test01()
{
  int * p = func();
  cout << *p << endl;
  cout << *p << endl;
  cout << *p << endl;
  cout << *p << endl;
  //堆区的数据 由程序员管理开辟，程序员管理释放
  //如果想释放堆区的数据，利用关键字delete
  delete p;
  //cout<<*p<<endl;  由于已经delete释放了再次访问会报错
}

// 2 在堆区利用new开辟数组
void test02()
{
    //创建10个整形数据的数组，在堆区
    int * arr = new int[10];
    
    for (int i = 0; i < 10; i++)
    {
        arr[i] = i + 100;//给10个元素复制 100 ~ 109
    }

    for (int i = 0; i < 10; i++)
    {
        cout << arr[i] << endl;
    }
    
    //释放
    //释放数组要加[]
    delete[] arr;
}


int main(void)
{ 
    test01();

    test02();

    system("pause");
    return 0;
}
```

