# GDB

> [GDB](http://www.sourceware.org/gdb/)是GNU组织的开源项目，你可以使用gdb调试一个程序，或者查看程序dump时程序在做什么？

这本文档会按照以你要达成什么目的，有什么需要，想要gdb做什么来撰写，本文对gdb的使用基于C语言的程序调试，当然gdb也可以应用在c++等的调试，但c语言的简单、门槛或许对这样的基础教程覆盖更广的人群。当然，绝大多数的调试都是举一反三通用的，希望对你有所帮助。

# 入门

## 安装gdb

### windows
### ubuntu

## 开始调试

**编译程序**

```
/** 示例程序 */
#include <stdio.h>

typedef struct
{
    char name[5];
    float weight;
}s_simple;

int b = 1;              // 全局变量

int main(int argc, char* args[])
{
    int a = 0;          // 局部变量
    s_simple simple =   // 结构体 
    {
        .weight = 0.1,
    };

    a++;
    b++;

    printf("这是一个简单的示例程序，将会使用它进行简单的gdb功能演示\n");
    printf("a = %d, b = %d, simple.weight = %f", a, b, simple.weight);

    return 0;
}

```

* 编译添加-g选项
```
使用gcc编译，指定编译结果名为simple.out
gcc -g simple.c -o simple.out
```

* 使用gdb附加到程序进行调试
```
[root@P3 study]# gdb ./simple.out 
GNU gdb (GDB) 8.2
Copyright (C) 2018 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-pc-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<http://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from ./simple.out...done.
(gdb) 
```


## breakpoint

## local

## stack

## registers

## asm

## 参考

****