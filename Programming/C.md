# C 语言

## 1. 简介

助记符，汇编语言。

计算机语言：人和计算机交流的语言。

1972年上线，面向过程，由B语言发展而来，贝尔实验室。

国际标准：C89/C90

广泛应用于底层软件开发(OS, 驱动)。

```c
#include <stdio.h>
int main()
{
	printf("Hello World\n");
	return 0;
}
```

## 2. 数据类型

### 2.1 基本类型

| 类型	   |长度(Byte)      |
| --------- | ---- |
| char       | 1 |
| short | 2 |
| int  | 4 |
| long      | 4 (C语言标准：sizeof(long)>=sizeof(int) 就可以了) |
| long long | 8 |
| float     | 4 |
| double    | 8 |

### 2.2 构造类型

### 2.2.1 数组

`int arr[10] = {1, 2, 3, 4, 5}`: 不完全初始化，剩余默认为0.

## 3. 变量与常量

### 3.1 变量
|          | 局部变量         | 全局变量                                                   |
| -------- | ---------------- | ---------------------------------------------------------- |
| 位置     | 在大括号内部     | 在大括号外部                                               |
| 作用域   | 变量所在局部范围 | 整个工程 （使用时需要声明外部文件定义的extern int g_val;） |
| 生命周期 | 作用域内         | 作用域内（程序的生命周期）                                 |
|          |                  |                                                            |

### 3.2 常量

|            |                                                              |
| ---------- | ------------------------------------------------------------ |
| 字面常量   | 3.14，10 ，‘a’， ”hello“                                     |
| 常变量     | const 修饰的                                                 |
| 标识符常量 | define是一个预处理指令 <br />#define MAX 1000. 定义了一个常量<br />#define ADD(X,Y) X+Y .定义了宏 (宏就是替换) 4\*ADD(2, 3) = 4\*2 + 3 |
| 枚举常量   |                                                              |

```c
enum Sex					enum Sex         
{							{
	MALE,		or				MALE = 3,
    FEMALE						FEMALE
}							}
// 每个值默认从0开始
```

## 4. 字符串

双引号。隐式最后一个字符是`\0`, 这是字符串的结束标志。

char arr[] = “hello”; or char arr[] = {'a', 'b' ,'c', '\0'};

```c
#include <string.h>
int len = strlen("abc"); // 3
```

`??)` : 三字母词，等于 ]

`\a` : 响铃

`\123` : 跟一至三个八进制数字

`\x12`: 跟两个十六进制数字

## 5. 循环

1. while
2. do while

## 6. 常见关键字

| 关键字            |                                                              |
| ----------------- | ------------------------------------------------------------ |
| auto              | 局部变量默认都是用auto修饰的. 自动创建自动销毁               |
| extern            | 用来声明外部符号的。                                         |
| register          | 建议将该值存放到寄存器中。                                   |
| typedef 原名 新名 | 类型重定义                                                   |
| static            | 修饰局部变量，只初始化一次，方法结束不销毁。<br />修饰全局变量，只能在自己所在源文件使用，切断外部链接。<br />修饰函数，只能在自己所在源文件使用，切断外部链接。 |

## 7. 指针

指针变量。

大小：所有类型指针大小相同。

## 8. 结构体

```c
struct Stu
{
    char name[20];
    int age;
}
struct Stu s = { "zs" , 20};
s.name;
```

## 9. 流程控制

switch （整型表达式）


## NOTE:

### 1. visual studio快捷键
| Ctrl + F5                            | 编译+链接+运行     |
| ------------------------------------ | ------------------ |
| Ctrl + L                             | 删除一行           |
| Ctrl k-> Ctrl c<br />Ctrl k-> Ctrl u | 注释<br />取消注释 |
|                                      |                    |
### 2. 内置函数
| printf("Hello World");<br />printf(“%d\n”, sizeof(a)); | <stdio.h>, <br />%d：整数<br />%f: float<br />%lf: double<br />%s: 字符串<br />%p: 地址 |
| ------------------------------------------------------ | ------------------------------------------------------------ |
| scanf(“%d %d”，&a, &b);                                | 输入函数，scanf_s是VS自带的                                  |
|                                                        |                                                              |
|                                                        |                                                              |
### 3. 

`~` : 所有二进制位取反。整数在内存中存的是补码。

`, ` : 逗号操作符，从左向右一次执行，赋值时会使用最后一个表达式的值

## THE END
