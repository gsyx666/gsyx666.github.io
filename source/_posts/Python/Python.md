---
title: Python
author: gsyx
tags:
  - Python
categories:
  - Python
date: 2022-10-01 16:54:00
---



> https://github.com/jackfrued/Python-100-Days
> [前言 · explore-python (gitbooks.io)](https://funhacks.gitbooks.io/explore-python/content/)
> https://www.liaoxuefeng.com/wiki/1016959663602400
> https://github.com/jerry-git/learn-python3 学习 Python 3 的实例教程。通过各种可以在网页运行的小例子，学习 Python 3
> https://github.com/facert/python-data-structure-cn/pulse
> https://github.com/piglei/one-python-craftsman
> https://automatetheboringstuff.com/
> [如何使用 Python3 编程](https://www.digitalocean.com/community/tutorials/digitalocean-ebook-how-to-code-in-python)
> [如何使用 Python 和 Tor 改变 IP 地址](https://boredhacking.com/tor-webscraping-proxy/)（英文）有的网站对爬虫有 IP 限制，该文作者将爬虫放在 Tor 网络后面，使得每次请求都有不一样的 IP 地址，从而避开限制。
> [wtfpython-cn](https://github.com/leisurelicht/wtfpython-cn)这个仓库收集一些有趣且鲜为人知的 Python 特性，内容是从英语翻译而来的
> [Python 编程基础](https://siteproxy.gsyx.workers.dev/https/archive.org/details/2018Fundamentals.ofPython)（PDF）免费英文电子书
> [社交媒体挖掘](http://socialdata.site/)免费书籍，介绍如何使用 Python 数据收集和分析社交媒体数据。
> [Python 开发最佳实践指南](https://pythonguidecn.readthedocs.io/zh/latest/)开源的中文电子书，翻译自英语原版，介绍 Python 语言的用法。
> [免费的 Python 英文书籍](https://www.pythonkitchen.com/legally-free-python-books-list/)
> [What the f*ck Python!](https://github.com/leisurelicht/wtfpython-cn)这个仓库是原始英文版的中文翻译，收集 Python 语言的各种怪异的语法点，以及鲜为人知的功能特性，并尝试讨论这些语法现象背后真正的原理。
> [免费的 Python 书籍](https://github.com/pamoroso/free-python-books)这个仓库收集网上的 Python 免费书籍（英文）。
> [学习 Python 的正确方法](https://learnpythontherightway.com/) 针对初学者的 Python 教程，提供 PDF 文件下载。
> [Nuitka](https://github.com/Nuitka/Nuitka) 一个用 Python 语言写的 Python 编译器，可以取代 CPython
> [DropsDevopsOrg/ECommerceCrawlers: 实战🐍多种网站、电商数据爬虫🕷。包含🕸：淘宝商品、微信公众号、大众点评、企查查、招聘网站、闲鱼、阿里任务、博客园、微博、百度贴吧、豆瓣电影、包图网、全景网、豆瓣音乐、某省药监局、搜狐新闻、机器学习文本采集、fofa资产采集、汽车之家、国家统计局、百度关键词收录数、蜘蛛泛目录、今日头条、豆瓣影评、携程、小米应用商店、安居客、途家民宿❤️❤️❤️。微信爬虫展示项目: (github.com)](https://github.com/DropsDevopsOrg/ECommerceCrawlers)
> [如何学Python？ | 卡瓦邦噶！ (kawabangga.com)](https://www.kawabangga.com/how-to-learn-python)
> [一篇文章让你彻底掌握 Python | dunwu.github.io](https://dunwu.github.io/docs/programming/python.html)
> https://learnxinyminutes.com/docs/python/
> tairraos.github.io/IntermediatePython/
> https://www.mssqltips.com/sqlservertip/7217/functions-in-python-code-samples/ 15 个重要的 Python 内置函数



```bash
python -m pip install --upgrade pip -i https://pypi.tuna.tsinghua.edu.cn/simple some-package

# 可以通过`pip search`命令根据名字查找需要的三方库，可以通过`pip list`命令来查看已经安装过的三方库。如果想更新某个三方库，可以使用`pip install -U`或`pip install --upgrade`；如果要删除某个三方库，可以使用`pip uninstall`命令。 
```

> **程序是指令的集合**，**写程序就是用指令控制计算机做我们想让它做的事情**。

> 计算机的硬件系统通常由五大部件构成，包括：**运算器**、**控制器**、**存储器**、**输入设备**和**输出设备**。其中，运算器和控制器放在一起就是我们常说的**中央处理器**，它的功能是执行各种运算和控制指令。刚才我们提到过程序是指令的集合，写程序就是将一系列的指令按照某种方式组织到一起，然后通过这些指令去控制计算机做我们想让它做的事情。目前，我们使用的计算机基本都是“冯·诺依曼体系结构”的计算机，这种计算机有两个关键点：一是要将**存储设备与中央处理器分开**；二是将**数据以二进制方式编码**。

> 二进制是一种“逢二进一”的计数法，跟我们人类使用的“逢十进一”的计数法本质是一样的。人类因为有十根手指所以使用了十进制，因为在计数时十根手指用完之后就只能用进位的方式来表示更大的数值。对于计算机来说，二进制在物理器件上最容易实现的，因为可以用高电压表示1，用低电压表示0。所以**计算机是使用二进制计数的**，不管什么**数据到了计算机内存中都是以二进制形式存在的**。

> 需要说明的是，不同于C++、Java等编程语言，Python中没有用花括号来构造代码块而是**使用了缩进的方式来表示代码的层次结构**。


## 基础

### 字符编码

### 变量

#### 变量和类型

在编程语言中，**变量是数据的载体**，简单的说就是一块用来保存数据的内存空间。**变量的值可以被读取和修改**，这是所有计算和控制的基础。计算机能处理的数据有很多种类型，最常见的就是数值，除了数值之外还有文本、图形、音频、视频等各种各样的数据。虽然数据在计算机中都是以二进制形态存在的，但是我们可以用不同类型的变量来表示数据类型的差异。**Python中的数据类型很多**，而且也**允许我们自定义新的数据类型**。

这里我们需要先了解几种常用的数据类型。

-   整型（`int`）：Python 中可以处理任意大小的整数，而且支持二进制（如`0b100`，换算成十进制是4）、八进制（如`0o100`，换算成十进制是64）、十进制（`100`）和十六进制（`0x100`，换算成十进制是256）的表示法。
-   浮点型（`float`）：浮点数也就是小数，之所以称为浮点数，是因为按照科学记数法表示时，一个浮点数的小数点位置是可变的，浮点数除了数学写法（如`123.456`）之外还支持科学计数法（如`1.23456e2`）。
-   字符串型（`str`）：字符串是以单引号或双引号括起来的任意文本，比如`'hello'`和`"hello"`。
-   布尔型（`bool`）：布尔值只有`True`、`False`两种值，要么是`True`，要么是`False`。

#### 变量命名

在Python中，变量命名需要遵循以下这些规则。

-   硬性规则：
    -   规则1：变量名由**字母**、数字和**下划线**构成，数字不能开头。需要说明的是，这里说的字母指的是Unicode字符，Unicode称为万国码，囊括了世界上大部分的文字系统，这也就意味着中文、日文、希腊字母等都可以作为变量名中的字符，但是像`!`、`@`、`#`这些特殊字符是不能出现在变量名中的，而且我们强烈建议大家**尽可能使用英文字母**。
    -   规则2：**大小写敏感**，简单的说就是大写的`A`和小写的`a`是两个不同的变量。
    -   规则3：变量名**不要跟Python语言的关键字**（有特殊含义的单词，后面会讲到）和**保留字**（如已有的函数、模块等的名字）**发生重名的冲突**。
-   非硬性规则：
    -   规则1：变量名通常使用小写英文字母，多个单词用下划线进行连接。
    -   规则2：受保护的变量用单个下划线开头。
    -   规则3：私有的变量用两个下划线开头。

规则2和规则3大家暂时不用理解，后面自然会明白的。当然，作为一个专业的程序员，给变量（事实上应该是所有的标识符）命名时做到**见名知意**也非常重要。

在 Python 程序中，我们可以**使用变量来保存数据**，**变量有不同的类型**，**变量可以做运算**，**也可以通过内置函数来转换变量类型**。
-   `int()`：将一个数值或字符串转换成整数，可以指定进制。
-   `float()`：将一个字符串转换成浮点数。
-   `str()`：将指定的对象转换成字符串形式，可以指定编码。
-   `chr()`：将整数转换成该编码对应的字符串（一个字符）。
-   `ord()`：将字符串（一个字符）转换成对应的编码（整数）。

```python
a = 45          # 变量a保存了45
b = 12.345         # 变量b保存了 12.345
c = 'hello, world'
d = True
# 使用type()检查变量的类型
print(type(a))    # <class 'int'>
print(type(b))    # <class 'float'>
# 整数转成浮点数
print(float(a))    # 100.0
# 浮点型转成字符串 (输出字符串时不会看到引号哟)
print(str(b))      # 12.345
```

### 运算符

| 运算符                                                       | 描述                           |
| ------------------------------------------------------------ | ------------------------------ |
| `[]` `[:]`                                                   | 下标，切片                     |
| `**`                                                         | 指数                           |
| `~` `+` `-`                                                  | 按位取反, 正负号               |
| `*` `/` `%` `//`                                             | 乘，除，模，整除               |
| `+` `-`                                                      | 加，减                         |
| `>>` `<<`                                                    | 右移，左移                     |
| `&`                                                          | 按位与                         |
| `^` `\|`                                                      | 按位异或，按位或               |
| `<=` `<` `>` `>=`                                            | 小于等于，小于，大于，大于等于 |
| `==` `!=`                                                    | 等于，不等于                   |
| `is`  `is not`                                               | 身份运算符                     |
| `in` `not in`                                                | 成员运算符                     |
| `not` `or` `and`                                             | 逻辑运算符                     |
| `=` `+=` `-=` `*=` `/=` `%=` `//=` `**=` `&=` `|=` `^=` `>>=` `<<=` | （复合）赋值运算符             |

>**说明：** 上面这个表格实际上是按照运算符的优先级从上到下列出了各种运算符。在实际开发中，如果搞不清楚运算符的优先级，可以使用圆括号来确保运算的执行顺序。

**逻辑运算符有三个，分别是`and`、`or`和`not`**。
- `and`字面意思是“而且”，所以`and`运算符会连接两个布尔值，如果两个布尔值都是`True`，那么运算的结果就是`True`；左右两边的布尔值有一个是`False`，最终的运算结果就是`False`。相信大家已经想到了，如果`and`左边的布尔值是`False`，不管右边的布尔值是什么，最终的结果都是`False`，所以在做运算的时候右边的值会被跳过（短路处理），这也就意味着在`and`运算符左边为`False`的情况下，右边的表达式根本不会执行。
- `or`字面意思是“或者”，所以`or`运算符也会连接两个布尔值，如果两个布尔值有任意一个是`True`，那么最终的结果就是`True`。当然，`or`运算符也是有短路功能的，在它左边的布尔值为`True`的情况下，右边的表达式根本不会执行。
- **`not`运算符的后面会跟上一个布尔值**，它的作用是得到与该布尔值相反的值，也就是说，`not`后面的布尔值如果是`True`，运算结果就是`False`；而`not`后面的布尔值如果是`False`，运算结果就是`True`。

```python
flag0 = 1 == 1 # flag0 = True
flag1 = 3 > 2  # flag1 = True
flag2 = 2 < 1  # flag2 = False
flag3 = flag1 and flag2  # flag3 = False
flag4 = flag1 or flag2   # flag4 = True
flag5 = not (1 != 2)     # flag5 = False
```
**说明**：比较运算符的优先级高于赋值运算符，所以`flag0 = 1 == 1`先做`1 == 1`产生布尔值`True`，再将这个值赋值给变量`flag0`。


## 数据结构

### 字符串

所谓**字符串**，就是**由零个或多个字符组成的有限序列**。在Python程序中，如果我们把单个或多个字符用单引号或者双引号包围起来，就可以表示一个字符串。
```python
s1 = 'hello, world!'
s2 = "你好，世界！"
print(s1, s2)
# 以三个双引号或单引号开头的字符串可以折行
s3 = '''
hello, 
world!
'''
print(s3, end='')
```

> **提示**：`print`函数中的`end=''`表示输出后不换行，即将默认的结束符`\n`（换行符）更换为`''`（空字符）。

**转义字符：**
可以在字符串中使用`\`（反斜杠）来表示转义，也就是说`\`后面的字符不再是它原来的意义，例如：`\n`不是代表反斜杠和字符`n`，而是表示换行；`\t`也不是代表反斜杠和字符`t`，而是表示制表符。所以如果字符串本身又包含了`'`、`"`、`\`这些特殊的字符，必须要通过`\`进行转义处理。

**原始字符串：**
Python 中的字符串可以`r`或`R`开头，这种字符串被称为原始字符串。意思是字符串中的每个字符都是它本来的含义，没有所谓的转义字符。

Python 中还允许在`\`后面跟一个八进制或者十六进制数来表示字符。例如`\141`和`\x61`都代表小写字母`a`，前者是八进制的表示法，后者是十六进制的表示法。另外一种表示字符的方式是在`\u`后面跟 Unicode 字符编码，例如`\u9a86\u660a`代表的是中文“骆昊”。

#### 字符串的运算

**拼接和重复**

我们可以使用`+`运算符来实现字符串的拼接，可以使用`*`运算符来重复一个字符串的内容，可以使用`in`和`not in`来判断一个字符串是否包含另外一个字符串，我们也可以用`[]`和`[:]`运算符从字符串取出某个字符或某些字符。

```python
s1 = 'hello' + ' ' + 'world'  # hello world 
s2 = '!' * 3 # !!!  
s1 += s2     # s1 = s1 + s2  s1=hello world!!!
s1 *= 2      # s1 = s1 * 2 s1=hello world!!!hello world!!!   
```

**比较运算**

对于两个字符串类型的变量，可以直接使用比较运算符比较两个字符串的相等性或大小。

需要说明的是，因为字符串在计算机内存中也是以二进制形式存在的，那么字符串的大小比较比的是每个字符对应的编码的大小。

例如`A`的编码是`65`， 而`a`的编码是`97`，所以`'A' < 'a'`的结果相当于就是`65 < 97`的结果，很显然是`True`；而`'boy' < 'bad'`，因为第一个字符都是`'b'`比不出大小，所以实际比较的是第二个字符的大小，显然`'o' < 'a'`的结果是`False`，所以`'boy' < 'bad'`的结果也是`False`。如果不清楚两个字符对应的编码到底是多少，可以使用`ord`函数来获得，例如`ord('A')`的值是`65`，而`ord('昊')`的值是`26122`。下面的代码为大家展示了字符串的比较运算。

```python
s1 = 'a whole new world'
s2 = 'hello world'
print(s1 == s2, s1 < s2)      # False True
print(s2 == 'hello world')    # True
print(s2 == 'HELLO world')    # False
print(s2 != 'HELLO world')    # True
s3 = '骆昊'
print(ord('骆'), ord('昊'))               # 39558 26122
s4 = '王大锤'
print(ord('王'), ord('大'), ord('锤'))    # 29579 22823 38180
print(s3 > s4, s3 <= s4)      # True False
```

需要强调一下的是，**字符串的比较运算比较的是字符串的内容**。

Python 中还有一个`is`运算符（身份运算符），如果用`is`来比较两个字符串，它比较的是两个变量对应的字符串对象的内存地址，简单的说就是两个变量是否对应内存中的同一个字符串。看看下面的代码就比较清楚`is`运算符的作用了。

```python
s1 = 'hello world'
s2 = 'hello world'
s3 = s2
# 比较字符串的内容
print(s1 == s2, s2 == s3)    # True True
# 比较字符串的内存地址
print(s1 is s2, s2 is s3)    # False True
```

**成员运算**

Python 中可以用`in`和`not in`判断一个字符串中是否存在另外一个字符或字符串。`in`和`not in`运算通常称为成员运算，会产生布尔值`True`或`False`。
```python
s1 = 'hello, world'
print('wo' in s1)    # True
s2 = 'goodbye'
print(s2 in s1)      # False
```

**获取字符串长度**

获取字符串长度没有直接的运算符，而是使用内置函数`len`。
```python
s = 'hello, world'
print(len(s))                   # 12
print(len('goodbye, world'))    # 14
```

**索引**

如果希望从字符串中取出某个字符，我们可以对字符串进行索引运算，运算符是`[n]`，其中`n`是一个整数。

假设字符串的长度为`N`，那么`n`可以是从`0`到`N-1`的整数，其中`0`是字符串中第一个字符的索引，而`N-1`是字符串中最后一个字符的索引，通常称之为正向索引；在 Python 中，字符串的索引也可以是从`-1`到`-N`的整数。其中`-1`是最后一个字符的索引，而`-N`则是第一个字符的索引，通常称之为负向索引。注意，因为**字符串是不可变类型**，所以**不能通过索引运算修改字符串中的字符**。
```python
s = 'abc123456'
N = len(s)
# 获取第一个字符
print(s[0], s[-N])    # a a

# 获取最后一个字符
print(s[N-1], s[-1])  # 6 6

# 获取索引为2或-7的字符
print(s[2], s[-7])    # c c

# 获取索引为5和-4的字符
print(s[5], s[-4])    # 3 3
```

需要提醒大家注意的是，在进行索引操作时，如果索引越界（正向索引不在`0`到`N-1`范围，负向索引不在`-1`到`-N`范围），会引发`IndexError`异常，错误提示信息为：`string index out of range`（字符串索引超出范围）。

**切片**

如果要从字符串中取出多个字符，我们可以对字符串进行切片。

运算符是`[i:j:k]`，其中`i`是开始索引，索引对应的字符可以取到；`j`是结束索引，索引对应的字符不能取到；`k`是步长，默认值为`1`，表示从前向后获取相邻字符的连续切片，所以`:k`部分可以省略。假设字符串的长度为`N`，当`k > 0`时表示正向切片（从前向后获取字符）。如果没有给出`i`和`j`的值，则`i`的默认值是`0`，`j`的默认值是`N`；当`k < 0`时表示负向切片（从后向前获取字符），如果没有给出`i`和`j`的值，则`i`的默认值是`-1`，j的默认值是`-N - 1`。如果不理解，直接看下面的例子，记住第一个字符的索引是`0`或`-N`，最后一个字符的索引是`N-1`或`-1`就行了。
```python
s = 'abc123456'

# i=2, j=5, k=1的正向切片操作
print(s[2:5])       # c12

# i=-7, j=-4, k=1的正向切片操作
print(s[-7:-4])     # c12

# i=2, j=9, k=1的正向切片操作
print(s[2:])        # c123456

# i=-7, j=9, k=1的正向切片操作
print(s[-7:])       # c123456

# i=2, j=9, k=2的正向切片操作
print(s[2::2])      # c246

# i=-7, j=9, k=2的正向切片操作
print(s[-7::2])     # c246

# i=0, j=9, k=2的正向切片操作
print(s[::2])       # ac246

# i=1, j=-1, k=2的正向切片操作
print(s[1:-1:2])    # b135

# i=7, j=1, k=-1的负向切片操作
print(s[7:1:-1])    # 54321c

# i=-2, j=-8, k=-1的负向切片操作
print(s[-2:-8:-1])  # 54321c

# i=7, j=-10, k=-1的负向切片操作
print(s[7::-1])     # 54321cba

# i=-1, j=1, k=-1的负向切片操作
print(s[:1:-1])     # 654321c

# i=0, j=9, k=1的正向切片
print(s[:])         # abc123456

# i=0, j=9, k=2的正向切片
print(s[::2])       # ac246

# i=-1, j=-10, k=-1的负向切片
print(s[::-1])      # 654321cba

# i=-1, j=-10, k=-2的负向切片
print(s[::-2])      # 642ca
```

**循环遍历每个字符**

如果希望从字符串中取出每个字符，可以使用`for`循环对字符串进行遍历，有两种方式。

方式一：
```python
s1 = 'hello'
for index in range(len(s1)):
    print(s1[index])
```
方式二：
```python
s1 = 'hello'
for ch in s1:
    print(ch)
```

#### 字符串的方法

在 Python 中，我们可以通过字符串类型自带的方法对字符串进行操作和处理，对于一个字符串类型的变量，我们可以用`变量名.方法名()`的方式来调用它的方法。所谓方法其实就是跟某个类型的变量绑定的函数，后面我们讲面向对象编程的时候还会对这一概念详加说明。

**大小写相关操作**

下面的代码演示了和字符串大小写变换相关的方法。
```python
s1 = 'hello, world!'

# 使用capitalize方法获得字符串首字母大写后的字符串
print(s1.capitalize())   # Hello, world!
# 使用title方法获得字符串每个单词首字母大写后的字符串
print(s1.title())        # Hello, World!
# 使用upper方法获得字符串大写后的字符串
print(s1.upper())        # HELLO, WORLD!

s2 = 'GOODBYE'
# 使用lower方法获得字符串小写后的字符串
print(s2.lower())        # goodbye
```

**查找操作**

如果想在一个字符串中从前向后查找有没有另外一个字符串，可以使用字符串的`find`或`index`方法。
```python
s = 'hello, world!'

# find方法从字符串中查找另一个字符串所在的位置
# 找到了返回字符串中另一个字符串首字符的索引
print(s.find('or'))        # 8
# 找不到返回-1
print(s.find('shit'))      # -1
# index方法与find方法类似
# 找到了返回字符串中另一个字符串首字符的索引
print(s.index('or'))       # 8
# 找不到引发异常
print(s.index('shit'))     # ValueError: substring not found
```
在使用`find`和`index`方法时还可以通过方法的参数来指定查找的范围，也就是查找不必从索引为`0`的位置开始。`find`和`index`方法还有逆向查找（从后向前查找）的版本，分别是`rfind`和`rindex`，代码如下所示。

```python
s = 'hello good world!'

# 从前向后查找字符o出现的位置(相当于第一次出现)
print(s.find('o'))       # 4
# 从索引为5的位置开始查找字符o出现的位置
print(s.find('o', 5))    # 7
# 从后向前查找字符o出现的位置(相当于最后一次出现)
print(s.rfind('o'))      # 12
```

**性质判断**

可以通过字符串的`startswith`、`endswith`来判断字符串是否以某个字符串开头和结尾；还可以用`is`开头的方法判断字符串的特征，这些方法都返回布尔值。
```python
s1 = 'hello, world!'

# startwith方法检查字符串是否以指定的字符串开头返回布尔值
print(s1.startswith('He'))    # False
print(s1.startswith('hel'))   # True
# endswith方法检查字符串是否以指定的字符串结尾返回布尔值
print(s1.endswith('!'))       # True

s2 = 'abc123456'

# isdigit方法检查字符串是否由数字构成返回布尔值
print(s2.isdigit())    # False
# isalpha方法检查字符串是否以字母构成返回布尔值
print(s2.isalpha())    # False
# isalnum方法检查字符串是否以数字和字母构成返回布尔值
print(s2.isalnum())    # True
```

**格式化字符串**

字符串类型可以通过`center`、`ljust`、`rjust`方法做居中、左对齐和右对齐的处理。如果要在字符串的左侧补零，也可以使用`zfill`方法。
```python
s = 'hello, world'

# center方法以宽度20将字符串居中并在两侧填充*
print(s.center(20, '*'))  # ****hello, world****
# rjust方法以宽度20将字符串右对齐并在左侧填充空格
print(s.rjust(20))        #         hello, world
# ljust方法以宽度20将字符串左对齐并在右侧填充~
print(s.ljust(20, '~'))   # hello, world~~~~~~~~
# 在字符串的左侧补零
print('33'.zfill(5))      # 00033
print('-33'.zfill(5))     # -0033
```
在用`print`函数输出字符串时，可以用下面的方式对字符串进行格式化。
```python
a = 321
b = 123
print('%d * %d = %d' % (a, b, a * b))
```
当然，我们也可以用字符串的方法来完成字符串的格式，代码如下所示。
```python
a = 321
b = 123
print('{0} * {1} = {2}'.format(a, b, a * b))
```
从Python 3.6开始，格式化字符串还有更为简洁的书写方式，就是在字符串前加上`f`来格式化字符串，在这种以`f`打头的字符串中，`{变量名}`是一个占位符，会被变量对应的值将其替换掉，代码如下所示。
```python
a = 321
b = 123
print(f'{a} * {b} = {a * b}')
```

如果需要进一步控制格式化语法中变量值的形式，可以参照下面的表格来进行字符串格式化操作。

| 变量值      | 占位符     | 格式化结果    | 说明 |
| ----------- | ---------- | ------------- | ---- |
| `3.1415926` | `{:.2f}`   | `'3.14'`      | 保留小数点后两位 |
| `3.1415926` | `{:+.2f}`  | `'+3.14'`       | 带符号保留小数点后两位 |
| `-1`        | `{:+.2f}`  | `'-1.00'` | 带符号保留小数点后两位 |
| `3.1415926` | `{:.0f}`   | `'3'` | 不带小数 |
| `123`       | `{:0>10d}` | `'0000000123'` | 左边补`0`，补够10位 |
| `123`       | `{:x<10d}` | `'123xxxxxxx'` | 右边补`x` ，补够10位 |
| `123`       | `{:>10d}`  | `'       123'` | 左边补空格，补够10位 |
| `123`       | `{:<10d}` | `'123       '` | 右边补空格，补够10位 |
| `123456789` | `{:,}`     | `'123,456,789'` | 逗号分隔格式 |
| `0.123`     | `{:.2%}`   | `'12.30%'`    | 百分比格式 |
| `123456789` | `{:.2e}`   | `'1.23e+08'`  | 科学计数法格式 |


**修剪操作**

字符串的`strip`方法可以帮我们获得将原字符串修剪掉左右两端空格之后的字符串。这个方法非常有实用价值，通常用来将用户输入中因为不小心键入的头尾空格去掉。`strip`方法还有`lstrip`和`rstrip`两个版本。
```python
s = '   jackfrued@126.com  \t\r\n'
# strip方法获得字符串修剪左右两侧空格之后的字符串
print(s.strip())    # jackfrued@126.com
```

**替换操作**

如果希望用新的内容替换字符串中指定的内容，可以使用`replace`方法。`replace`方法的第一个参数是被替换的内容，第二个参数是替换后的内容，还可以通过第三个参数指定替换的次数。
```python
s = 'hello, world'
print(s.replace('o', '@'))     # hell@, w@rld
print(s.replace('o', '@', 1))  # hell@, world
```

**拆分/合并操作**

可以使用字符串的`split`方法将一个字符串拆分为多个字符串（放在一个列表中），也可以使用字符串的`join`方法将列表中的多个字符串连接成一个字符串。
```python
s = 'I love you'
words = s.split()
print(words)            # ['I', 'love', 'you']
print('#'.join(words))  # I#love#you
```
需要说明的是，`split`方法默认使用空格进行拆分，我们也可以指定其他的字符来拆分字符串，而且还可以指定最大拆分次数来控制拆分的效果。
```python
s = 'I#love#you#so#much'
words = s.split('#')
print(words)  # ['I', 'love', 'you', 'so', 'much']
words = s.split('#', 3)
print(words)  # ['I', 'love', 'you', 'so#much']
```

**编码/解码操作**

Python 中除了字符串`str`类型外，还有一种表示二进制数据的字节串类型（`bytes`）。所谓字节串，就是**由零个或多个字节组成的有限序列**。通过字符串的`encode`方法，我们可以按照某种编码方式将字符串编码为字节串，我们也可以使用字节串的`decode`方法，将字节串解码为字符串。
```python
a = '骆昊'
b = a.encode('utf-8')
c = a.encode('gbk')
print(b, c)  # b'\xe9\xaa\x86\xe6\x98\x8a' b'\xc2\xe6\xea\xbb'
print(b.decode('utf-8'))
print(c.decode('gbk'))
```
注意，如果编码和解码的方式不一致，会导致乱码问题（无法再现原始的内容）或引发`UnicodeDecodeError`错误导致程序崩溃。


**其他方法**

对于字符串类型来说，还有一个常用的操作是对字符串进行匹配检查，即检查字符串是否满足某种特定的模式。例如，一个网站对用户注册信息中用户名和邮箱的检查，就属于模式匹配检查。实现模式匹配检查的工具叫做正则表达式，Python 语言通过标准库中的`re`模块提供了对正则表达式的支持。


## 分支结构

### if语句的使用
```python
x = float(input('x = '))
if x > 1:
    y = 3 * x - 5
elif x >= -1:
    y = x + 2
else:
    y = 5 * x + 3
print(f'f({x}) = {y}')
```

## 循环结构

### for-in循环
```python
"""
用for循环实现1~100求和
"""
total = 0
for x in range(1, 101):
    total += x
print(total)
```
`range(1, 101)`可以用来构造一个从`1`到`100`的范围，当我们把这样一个范围放到`for-in`循环中，就可以通过前面的循环变量`x`依次取出从`1`到`100`的整数。当然，`range`的用法非常灵活，下面给出了一个例子：

-   `range(101)`：可以用来产生0到100范围的整数，需要注意的是取不到101。
-   `range(1, 101)`：可以用来产生1到100范围的整数，相当于前面是闭区间后面是开区间。
-   `range(1, 101, 2)`：可以用来产生1到100的奇数，其中2是步长，即每次递增的值。
-   `range(100, 0, -2)`：可以用来产生100到1的偶数，其中-2是步长，即每次递减的值。
-   
### while循环
```python
"""
猜数字游戏

Version: 0.1
Author: 骆昊
"""
import random

# 产生一个1-100范围的随机数
answer = random.randint(1, 100)
counter = 0
while True:
    counter += 1
    number = int(input('请输入: '))
    if number < answer:
        print('大一点')
    elif number > answer:
        print('小一点')
    else:
        print('恭喜你猜对了!')
        break
# 当退出while循环的时候显示用户一共猜了多少次
print(f'你总共猜了{counter}次')
```

### break和continue

我们使用了`break`关键字，它的作用是提前结束循环。需要注意的是，`break`只能终止它所在的那个循环，这一点在使用嵌套循环结构时需要引起注意，下面的例子我们会讲到什么是嵌套的循环结构。

除了`break`之外，还有另一个关键字是`continue`，它可以用来放弃本次循环后续的代码直接让循环进入下一轮。

### 嵌套的循环结构

和分支结构一样，循环结构也是可以嵌套的，也就是说在循环中还可以构造循环结构。下面的例子演示了如何通过嵌套的循环来输出一个乘法口诀表（九九表）。

```python
"""
打印乘法口诀表
Version: 0.1
Author: 骆昊
"""
for i in range(1, 10):
    for j in range(1, i + 1):
        print(f'{i}*{j}={i * j}', end='\t')
    print()
```

## 数据结构

### 列表

可以使用`[]`字面量语法来定义列表，列表中的多个元素用逗号进行分隔，代码如下所示。
```
items1 = [35, 12, 99, 68, 55, 87]
items2 = ['Python', 'Java', 'Go', 'Kotlin']
```

除此以外，还可以通过Python内置的`list`函数将其他序列变成列表。准确的说，`list`并不是一个普通的函数，它是创建列表对象的构造器（后面会讲到对象和构造器这两个概念）。
```
items1 = list(range(1, 10))
print(items1)    # [1, 2, 3, 4, 5, 6, 7, 8, 9]
items2 = list('hello')
print(items2)    # ['h', 'e', 'l', 'l', 'o']
```

#### 列表的运算符
```python
items1 = [35, 12, 99, 68, 55, 87]
items2 = [45, 8, 29]

# 列表的拼接
items3 = items1 + items2
print(items3)    # [35, 12, 99, 68, 55, 87, 45, 8, 29]

# 列表的重复
items4 = ['hello'] * 3
print(items4)    # ['hello', 'hello', 'hello']

# 列表的成员运算
print(100 in items3)        # False
print('hello' in items4)    # True

# 获取列表的长度(元素个数)
size = len(items3)
print(size)                 # 9

# 列表的索引
print(items3[0], items3[-size])        # 35 35
items3[-1] = 100
print(items3[size - 1], items3[-1])    # 100 100

# 列表的切片
print(items3[:5])          # [35, 12, 99, 68, 55]
print(items3[4:])          # [55, 87, 45, 8, 100]
print(items3[-5:-7:-1])    # [55, 68]
print(items3[::-2])        # [100, 45, 55, 99, 35]

# 列表的比较运算
items5 = [1, 2, 3, 4]
items6 = list(range(1, 5))
# 两个列表比较相等性比的是对应索引位置上的元素是否相等
print(items5 == items6)    # True
items7 = [3, 2, 1]
# 两个列表比较大小比的是对应索引位置上的元素的大小
print(items5 <= items7)    # True
```

值得一提的是，由于列表是可变类型，所以通过索引操作既可以获取列表中的元素，也可以更新列表中的元素。对列表做索引操作一样要注意索引越界的问题，对于有`N`个元素的列表，正向索引的范围是`0`到`N-1`，负向索引的范围是`-1`到`-N`，如果超出这个范围，将引发`IndexError`异常，错误信息为：`list index out of range`。

#### 列表元素的遍历
```python
方法一：

items = ['Python', 'Java', 'Go', 'Kotlin']

for index in range(len(items)):
    print(items[index])

方法二：

items = ['Python', 'Java', 'Go', 'Kotlin']

for item in items:
    print(item)

```

#### 列表的方法

****添加和删除元素**** 
```python
items = ['Python', 'Java', 'Go', 'Kotlin']

# 使用append方法在列表尾部添加元素
items.append('Swift')
print(items)    # ['Python', 'Java', 'Go', 'Kotlin', 'Swift']
# 使用insert方法在列表指定索引位置插入元素
items.insert(2, 'SQL')
print(items)    # ['Python', 'Java', 'SQL', 'Go', 'Kotlin', 'Swift']

# 删除指定的元素
items.remove('Java')
print(items)    # ['Python', 'SQL', 'Go', 'Kotlin', 'Swift']
# 删除指定索引位置的元素
items.pop(0)
items.pop(len(items) - 1)
print(items)    # ['SQL', 'Go', 'Kotlin']

# 清空列表中的元素
items.clear()
print(items)    # []
```

需要提醒大家，在使用`remove`方法删除元素时，如果要删除的元素并不在列表中，会引发`ValueError`异常，错误消息是：`list.remove(x): x not in list`。在使用`pop`方法删除元素时，如果索引的值超出了范围，会引发`IndexError`异常，错误消息是：`pop index out of range`。

从列表中删除元素其实还有一种方式，就是使用Python中的`del`关键字后面跟要删除的元素，这种做法跟使用`pop`方法指定索引删除元素没有实质性的区别，但后者会返回删除的元素，前者在性能上略优（`del`对应字节码指令是`DELETE_SUBSCR`，而`pop`对应的字节码指令是`CALL_METHOD`和`POP_TOP`，不理解就跳过，不用管它！！！）。
```
items = ['Python', 'Java', 'Go', 'Kotlin']
del items[1]
print(items)    # ['Python', 'Go', 'Kotlin']
```

**元素位置和次数**

列表类型的`index`方法可以查找某个元素在列表中的索引位置；因为列表中允许有重复的元素，所以列表类型提供了`count`方法来统计一个元素在列表中出现的次数。请看下面的代码。
```
items = ['Python', 'Java', 'Java', 'Go', 'Kotlin', 'Python']

# 查找元素的索引位置
print(items.index('Python'))       # 0
print(items.index('Python', 2))    # 5
# 注意：虽然列表中有'Java'，但是从索引为3这个位置开始后面是没有'Java'的
print(items.index('Java', 3))      # ValueError: 'Java' is not in list
```
再来看看下面这段代码。
```
items = ['Python', 'Java', 'Java', 'Go', 'Kotlin', 'Python']

# 查找元素出现的次数
print(items.count('Python'))    # 2
print(items.count('Go'))        # 1
print(items.count('Swfit'))     # 0

```

**元素排序和反转**

列表的`sort`操作可以实现列表元素的排序，而`reverse`操作可以实现元素的反转，代码如下所示。
```
items = ['Python', 'Java', 'Go', 'Kotlin', 'Python']

# 排序
items.sort()
print(items)    # ['Go', 'Java', 'Kotlin', 'Python', 'Python']
# 反转
items.reverse()
print(items)    # ['Python', 'Python', 'Kotlin', 'Java', 'Go']
```
### 列表的生成式

在Python中，列表还可以通过一种特殊的字面量语法来创建，这种语法叫做生成式。我们给出两段代码，大家可以做一个对比，看看哪一种方式更加简单优雅。

通过`for`循环为空列表添加元素。
```
# 创建一个由1到9的数字构成的列表
items1 = []
for x in range(1, 10):
    items1.append(x)
print(items1)

# 创建一个由'hello world'中除空格和元音字母外的字符构成的列表
items2 = []
for x in 'hello world':
    if x not in ' aeiou':
        items2.append(x)
print(items2)

# 创建一个由个两个字符串中字符的笛卡尔积构成的列表
items3 = []
for x in 'ABC':
    for y in '12':
        items3.append(x + y)
print(items3)
```
通过生成式创建列表。
```
# 创建一个由1到9的数字构成的列表
items1 = [x for x in range(1, 10)]
print(items1)    # [1, 2, 3, 4, 5, 6, 7, 8, 9]

# 创建一个由'hello world'中除空格和元音字母外的字符构成的列表
items2 = [x for x in 'hello world' if x not in ' aeiou']
print(items2)    # ['h', 'l', 'l', 'w', 'r', 'l', 'd']

# 创建一个由个两个字符串中字符的笛卡尔积构成的列表
items3 = [x + y for x in 'ABC' for y in '12']
print(items3)    # ['A1', 'A2', 'B1', 'B2', 'C1', 'C2']
```
下面这种方式不仅代码简单优雅，而且性能也优于上面使用`for`循环和`append`方法向空列表中追加元素的方式。可以简单跟大家交待下为什么生成式拥有更好的性能，那是因为Python解释器的字节码指令中有专门针对生成式的指令（`LIST_APPEND`指令）；而`for`循环是通过方法调用（`LOAD_METHOD`和`CALL_METHOD`指令）的方式为列表添加元素，方法调用本身就是一个相对耗时的操作。对这一点不理解也没有关系，记住“**强烈建议用生成式语法来创建列表**”这个结论就可以了。

#### 嵌套的列表

Python语言没有限定列表中的元素必须是相同的数据类型，也就是说一个列表中的元素可以任意的数据类型，当然也包括列表。如果列表中的元素又是列表，那么我们可以称之为嵌套的列表。嵌套的列表可以用来表示表格或数学上的矩阵，例如：我们想保存5个学生3门课程的成绩，可以定义一个保存5个元素的列表保存5个学生的信息，而每个列表元素又是3个元素构成的列表，分别代表3门课程的成绩。但是，一定要注意下面的代码是有问题的。
```
scores = [[0] * 3] * 5
print(scores)    # [[0, 0, 0], [0, 0, 0], [0, 0, 0], [0, 0, 0], [0, 0, 0]]
```
看上去我们好像创建了一个`5 * 3`的嵌套列表，但实际上当我们录入第一个学生的第一门成绩后，你就会发现问题来了，我们看看下面代码的输出。
```
# 嵌套的列表需要多次索引操作才能获取元素
scores[0][0] = 95
print(scores)
# [[95, 0, 0], [95, 0, 0], [95, 0, 0], [95, 0, 0], [95, 0, 0]]
```
我们不去过多的解释为什么会出现这样的问题，如果想深入研究这个问题，可以通过[Python Tutor](http://www.pythontutor.com/visualize.html)网站的可视化代码执行功能，看看创建列表时计算机内存中发生了怎样的变化，下面的图就是在这个网站上生成的。建议大家不去纠结这个问题，现阶段只需要记住不能用`[[0] * 3] * 5]`这种方式来创建嵌套列表就行了。那么创建嵌套列表的正确做法是什么呢，下面的代码会给你答案。
```
scores = [[0] * 3 for _ in range(5)]
scores[0][0] = 95
print(scores)
# [[95, 0, 0], [0, 0, 0], [0, 0, 0], [0, 0, 0], [0, 0, 0]]
```



## 函数和模块

> 世界级的编程大师_Martin Fowler_先生曾经说过：“**代码有很多种坏味道，重复是最坏的一种！**”。
> **函数是对功能相对独立且会重复使用的代码的封装**。

### 定义函数

数学上的函数通常形如`y = f(x)`或者`z = g(x, y)`这样的形式>在`y = f(x)`中，`f`是函数的名字，`x`是函数的自变量，`y`是函数的因变量；而在`z = g(x, y)`中，`g`是函数名，`x`和`y`是函数的自变量，`z`是函数的因变量。Python中的函数跟这个结构是一致的，每个函数都有自己的名字、自变量和因变量。我们通常把Python中函数的自变量称为函数的参数，而因变量称为函数的返回值。

在Python中可以使用`def`关键字来定义函数。在函数名后面的圆括号中可以放置传递给函数的参数，就是我们刚才说到的函数的自变量，而函数执行完成后我们会通过`return`关键字来返回函数的执行结果，就是我们刚才说的函数的因变量。一个函数要执行的代码块（要做的事情）也是通过缩进的方式来表示的，跟之前分支和循环结构的代码块是一样的。大家不要忘了`def`那一行的最后面还有一个`:`，之前提醒过大家，那是在英文输入法状态下输入的冒号。

我们可以通过函数对~~上面的代码~~进行重构。**所谓重构，是在不影响代码执行结果的前提下对代码的结构进行调整。**重构之后的代码如下所示。

```python
"""
输入M和N计算C(M,N)
Version: 0.1
Author: 骆昊
"""

# 定义函数：def是定义函数的关键字、fac是函数名，num是参数（自变量）
def fac(num):
    """求阶乘"""
    result = 1
    for n in range(1, num + 1):
        result *= n
    # 返回num的阶乘（因变量）
    return result

m = int(input('m = '))
n = int(input('n = '))
# 当需要计算阶乘的时候不用再写重复的代码而是直接调用函数fac
# 调用函数的语法是在函数名后面跟上圆括号并传入参数
print(fac(m) // fac(n) // fac(m - n))
```

> **说明**：事实上，Python标准库的`math`模块中有一个名为`factorial`的函数已经实现了求阶乘的功能，我们可以直接使用该函数来计算阶乘。**将来我们使用的函数，要么是自定义的函数，要么是Python标准库或者三方库中提供的函数**。


### 函数的参数

#### 参数的默认值

如果函数中没有`return`语句，那么函数默认返回代表空值的`None`。另外，在定义函数时，函数也可以没有自变量，**但是函数名后面的圆括号是必须有的**。Python中还允许函数的参数拥有默认值，我们可以把之前讲过的一个例子“CRAPS赌博游戏”中摇色子获得点数的功能封装成函数，代码如下所示。
```python
"""
参数的默认值
Version: 0.1
Author: 骆昊
"""
from random import randint

# 定义摇色子的函数，n表示色子的个数，默认值为2
def roll_dice(n=2):
    """摇色子返回总的点数"""
    total = 0
    for _ in range(n):
        total += randint(1, 6)
    return total

# 如果没有指定参数，那么n使用默认值2，表示摇两颗色子
print(roll_dice())
# 传入参数3，变量n被赋值为3，表示摇三颗色子获得点数
print(roll_dice(3))

我们再来看一个更为简单的例子。

def add(a=0, b=0, c=0):
    """三个数相加求和"""
    return a + b + c

# 调用add函数，没有传入参数，那么a、b、c都使用默认值0
print(add())         # 0
# 调用add函数，传入一个参数，那么该参数赋值给变量a, 变量b和c使用默认值0
print(add(1))        # 1
# 调用add函数，传入两个参数，1和2分别赋值给变量a和b，变量c使用默认值0
print(add(1, 2))     # 3
# 调用add函数，传入三个参数，分别赋值给a、b、c三个变量
print(add(1, 2, 3))  # 6
# 传递参数时可以不按照设定的顺序进行传递，但是要用“参数名=参数值”的形式
print(add(c=50, a=100, b=200))    # 350
```
> **注意**：带默认值的参数必须放在不带默认值的参数之后，否则将产生`SyntaxError`错误，错误消息是：`non-default argument follows default argument`，翻译成中文的意思是“没有默认值的参数放在了带默认值的参数后面”。

#### 变参数

接下来，我们还可以实现一个对任意多个数求和的`add`函数，因为**Python语言中的函数可以通过星号表达式语法来支持可变参数**。所谓可变参数指的是在调用函数时，可以向函数传入`0`个或任意多个参数。将来我们以团队协作的方式开发商业项目时，很有可能要设计函数给其他人使用，但有的时候我们并不知道函数的调用者会向该函数传入多少个参数，这个时候可变参数就可以派上用场。下面的代码演示了用可变参数实现对任意多个数求和的`add`函数。
```python
"""
可变参数
Version: 0.1
Author: 骆昊
"""

# 用星号表达式来表示args可以接收0个或任意多个参数
def add(*args):
    total = 0
    # 可变参数可以放在for循环中取出每个参数的值
    for val in args:
        if type(val) in (int, float):
            total += val
    return total

# 在调用add函数时可以传入0个或任意多个参数
print(add())
print(add(1))
print(add(1, 2))
print(add(1, 2, 3))
print(add(1, 3, 5, 7, 9))
```


### 用模块管理函数

Python中每个文件就代表了一个模块（module），我们在不同的模块中可以有同名的函数，在使用函数的时候我们通过`import`关键字导入指定的模块再使用**完全限定名**的调用方式就可以区分到底要使用的是哪个模块中的`foo`函数，代码如下所示。

`module1.py`
```python
def foo():
    print('hello, world!')
```
`module2.py`
```python
def foo():
    print('goodbye, world!')
```
`test.py`
```python
import module1
import module2

# 用“模块名.函数名”的方式（完全限定名）调用函数，
module1.foo()    # hello, world!
module2.foo()    # goodbye, world!
```
在导入模块时，还可以使用`as`关键字对模块进行别名，这样我们可以使用更为简短的完全限定名。

`test.py`
```python
import module1 as m1
import module2 as m2

m1.foo()    # hello, world!
m2.foo()    # goodbye, world!
```
上面的代码我们导入了定义函数的模块，我们也可以使用`from...import...`语法从模块中直接导入需要使用的函数，代码如下所示。

`test.py`
```python
from module1 import foo

foo()    # hello, world!

from module2 import foo

foo()    # goodbye, world!
```
但是，如果我们如果从两个不同的模块中导入了同名的函数，后导入的函数会覆盖掉先前的导入，就像下面的代码中，调用`foo`会输出`hello, world!`，因为我们先导入了`module2`的`foo`，后导入了`module1`的`foo` 。如果两个`from...import...`反过来写，就是另外一番光景了。

`test.py`
```python
from module2 import foo
from module1 import foo

foo()    # hello, world!
```
如果想在上面的代码中同时使用来自两个模块中的`foo`函数也是有办法的，大家可能已经猜到了，还是用`as`关键字对导入的函数进行别名，代码如下所示。

`test.py`
```python
from module1 import foo as f1
from module2 import foo as f2

f1()    # hello, world!
f2()    # goodbye, world!
```


### 标准库中的模块和函数

Python标准库中提供了大量的模块和函数来简化我们的开发工作，我们之前用过的`random`模块就为我们提供了生成随机数和进行随机抽样的函数；而`time`模块则提供了和时间操作相关的函数；上面求阶乘的函数在Python标准库中的`math`模块中已经有了，实际开发中并不需要我们自己编写，而`math`模块中还包括了计算正弦、余弦、指数、对数等一系列的数学函数。随着我们进一步的学习Python编程知识，我们还会用到更多的模块和函数。

Python标准库中还有一类函数是不需要`import`就能够直接使用的，我们将其称之为内置函数，这些内置函数都是很有用也是最常用的，下面的表格列出了一部分的内置函数。

| 函数    | 说明                                                         |
| ------- | ------------------------------------------------------------ |
| `abs`   | 返回一个数的绝对值，例如：`abs(-1.3)`会返回`1.3`。           |
| `bin`   | 把一个整数转换成以`'0b'`开头的二进制字符串，例如：`bin(123)`会返回`'0b1111011'`。 |
| `chr`   | 将Unicode编码转换成对应的字符，例如：`chr(8364)`会返回`'€'`。 |
| `hex`   | 将一个整数转换成以`'0x'`开头的十六进制字符串，例如：`hex(123)`会返回`'0x7b'`。 |
| `input` | 从输入中读取一行，返回读到的字符串。                         |
| `len`   | 获取字符串、列表等的长度。                                   |
| `max`   | 返回多个参数或一个可迭代对象中的最大值，例如：`max(12, 95, 37)`会返回`95`。 |
| `min`   | 返回多个参数或一个可迭代对象中的最小值，例如：`min(12, 95, 37)`会返回`12`。 |
| `oct`   | 把一个整数转换成以`'0o'`开头的八进制字符串，例如：`oct(123)`会返回`'0o173'`。 |
| `open`  | 打开一个文件并返回文件对象。                                 |
| `ord`   | 将字符转换成对应的Unicode编码，例如：`ord('€')`会返回`8364`。 |
| `pow`   | 求幂运算，例如：`pow(2, 3)`会返回`8`；`pow(2, 0.5)`会返回`1.4142135623730951`。 |
| `print` | 打印输出。                                                   |
| `range` | 构造一个范围序列，例如：`range(100)`会产生`0`到`99`的整数序列。 |
| `round` | 按照指定的精度对数值进行四舍五入，例如：`round(1.23456, 4)`会返回`1.2346`。 |
| `sum`   | 对一个序列中的项从左到右进行求和运算，例如：`sum(range(1, 101))`会返回`5050`。 |
| `type`  | 返回对象的类型，例如：`type(10)`会返回`int`；而` type('hello')`会返回`str`。 |


## 函数使用进阶

### 关键字参数

下面是一个判断传入的三条边长能否构成三角形的函数，在调用函数传入参数时，我们可以指定参数名，也可以不指定参数名，代码如下所示。
```python
def is_triangle(a, b, c):
    print(f'a = {a}, b = {b}, c = {c}')
    return a + b > c and b + c > a and a + c > b

# 调用函数传入参数不指定参数名按位置对号入座
print(is_triangle(1, 2, 3))
# 调用函数通过“参数名=参数值”的形式按顺序传入参数
print(is_triangle(a=1, b=2, c=3))
# 调用函数通过“参数名=参数值”的形式不按顺序传入参数
print(is_triangle(c=3, a=1, b=2))
```
在没有特殊处理的情况下，函数的参数都是**位置参数**，也就意味着传入参数的时候对号入座即可，如上面代码的第7行所示，传入的参数值`1`、`2`、`3`会依次赋值给参数`a`、`b`、`c`。当然，也可以通过`参数名=参数值`的方式传入函数所需的参数，因为指定了参数名，传入参数的顺序可以进行调整。

调用函数时，如果希望函数的调用者必须以`参数名=参数值`的方式传参，可以用**命名关键字参数**（keyword-only argument）取代位置参数。所谓命名关键字参数，是在函数的参数列表中，写在`*`之后的参数，代码如下所示。
```python
def is_triangle(*, a, b, c):
    print(f'a = {a}, b = {b}, c = {c}')
    return a + b > c and b + c > a and a + c > b

# TypeError: is_triangle() takes 0 positional arguments but 3 were given
# print(is_triangle(3, 4, 5))
# 传参时必须使用“参数名=参数值”的方式，位置不重要
print(is_triangle(a=3, b=4, c=5))
print(is_triangle(c=5, b=4, a=3))
```
> **注意**：上面的`is_triangle`函数，参数列表中的`*`是一个分隔符，`*`前面的参数都是位置参数，而`*`后面的参数就是命名关键字参数。

我们之前讲过在函数的参数列表中可以使用**可变参数**`*args`来接收任意数量的参数，但是我们需要看看，`*args`是否能够接收带参数名的参数。
```python
def calc(*args):
    result = 0
    for arg in args:
        if type(arg) in (int, float):
            result += arg
    return result

print(calc(a=1, b=2, c=3))
```
执行上面的代码会引发`TypeError`错误，错误消息为`calc() got an unexpected keyword argument 'a'`，由此可见，`*args`并不能处理带参数名的参数。我们在设计函数时，如果既不知道调用者会传入的参数个数，也不知道调用者会不会指定参数名，那么同时使用可变参数和**关键字参数**。关键字参数会将传入的带参数名的参数组装成一个字典，参数名就是字典中键值对的键，而参数值就是字典中键值对的值，代码如下所示。
```python
def calc(*args, **kwargs):
	# **kwargs 接收可变参数和关键字参数 使用*args和**kwargs接收所有参数
    result = 0
    for arg in args:
        if type(arg) in (int, float):
            result += arg
    for value in kwargs.values():
        if type(value) in (int, float):
            result += value
    return result

print(calc())                  # 0
print(calc(1, 2, 3))           # 6
print(calc(a=1, b=2, c=3))     # 6
print(calc(1, 2, c=3, d=4))    # 10
```
> **提示**：**不带参数名的参数（位置参数）必须出现在带参数名的参数（关键字参数）之前**，否则将会引发异常。例如，执行`calc(1, 2, c=3, d=4, 5)`将会引发`SyntaxError`错误，错误消息为`positional argument follows keyword argument`，翻译成中文意思是“位置参数出现在关键字参数之后”。

### 高阶函数的用法

在前面几节课中，我们讲到了面向对象程序设计，在面向对象的世界中，一切皆为对象，所以类和函数也是对象。函数的参数和返回值可以是任意类型的对象，这就意味着**函数本身也可以作为函数的参数或返回值**，这就是所谓的**高阶函数**。

如果我们希望上面的`calc`函数不仅仅可以做多个参数求和，还可以做多个参数求乘积甚至更多的二元运算，我们就可以使用高阶函数的方式来改写上面的代码，将加法运算从函数中移除掉，具体的做法如下所示。
```python
def calc(*args, init_value, op, **kwargs):
    result = init_value
    for arg in args:
        if type(arg) in (int, float):
            result = op(result, arg)
    for value in kwargs.values():
        if type(value) in (int, float):
            result = op(result, value)
    return result
```
注意，上面的函数增加了两个参数，其中`init_value`代表运算的初始值，`op`代表二元运算函数。经过改造的`calc`函数不仅仅可以实现多个参数的累加求和，也可以实现多个参数的累乘运算，代码如下所示。
```python
def add(x, y):
    return x + y

def mul(x, y):
    return x * y

print(calc(1, 2, 3, init_value=0, op=add, x=4, y=5))      # 15
print(calc(1, 2, x=3, y=4, z=5, init_value=1, op=mul))    # 120
```
通过对高阶函数的运用，`calc`函数不再和加法运算耦合，所以灵活性和通用性会变强，这是一种解耦合的编程技巧，但是最初学者来说可能会稍微有点难以理解。需要注意的是，将函数作为参数和调用函数是有显著的区别的，**调用函数需要在函数名后面跟上圆括号，而把函数作为参数时只需要函数名即可**。上面的代码也可以不用定义`add`和`mul`函数，因为Python标准库中的`operator`模块提供了代表加法运算的`add`和代表乘法运算的`mul`函数，我们直接使用即可，代码如下所示。
```python
import operator

print(calc(1, 2, 3, init_value=0, op=operator.add, x=4, y=5))      # 15
print(calc(1, 2, x=3, y=4, z=5, init_value=1, op=operator.mul))    # 120
```
Python内置函数中有不少高阶函数，我们前面提到过的`filter`和`map`函数就是高阶函数，前者可以实现对序列中元素的过滤，后者可以实现对序列中元素的映射，例如我们要去掉一个整数列表中的奇数，并对所有的偶数求平方得到一个新的列表，就可以直接使用这两个函数来做到，具体的做法是如下所示。
```python
def is_even(num):
    return num % 2 == 0

def square(num):
    return num ** 2

numbers1 = [35, 12, 8, 99, 60, 52]
numbers2 = list(map(square, filter(is_even, numbers1)))
print(numbers2)    # [144, 64, 3600, 2704]
```
当然，要完成上面代码的功能，也可以使用列表生成式，列表生成式的做法更为简单优雅。
```python
numbers1 = [35, 12, 8, 99, 60, 52]
numbers2 = [num ** 2 for num in numbers1 if num % 2 == 0]
print(numbers2)    # [144, 64, 3600, 2704]
```


### Lambda函数

在使用高阶函数的时候，如果作为参数或者返回值的函数本身非常简单，一行代码就能够完成，那么我们可以使用**Lambda函数**来表示。Python中的Lambda函数是没有的名字函数，所以很多人也把它叫做**匿名函数**，匿名函数只能有一行代码，代码中的表达式产生的运算结果就是这个匿名函数的返回值。上面代码中的`is_even`和`square`函数都只有一行代码，我们可以用Lambda函数来替换掉它们，代码如下所示。
```python
numbers1 = [35, 12, 8, 99, 60, 52]
numbers2 = list(map(lambda x: x ** 2, filter(lambda x: x % 2 == 0, numbers1)))
print(numbers2)    # [144, 64, 3600, 2704]
```
通过上面的代码可以看出，定义Lambda函数的关键字是`lambda`，后面跟函数的参数，如果有多个参数用逗号进行分隔；冒号后面的部分就是函数的执行体，通常是一个表达式，表达式的运算结果就是Lambda函数的返回值，不需要写`return` 关键字。

如果需要使用加减乘除这种简单的二元函数，也可以用Lambda函数来书写，例如调用上面的`calc`函数时，可以通过传入Lambda函数来作为`op`参数的参数值。当然，`op`参数也可以有默认值，例如我们可以用一个代表加法运算的Lambda函数来作为`op`参数的默认值。
```python
def calc(*args, init_value=0, op=lambda x, y: x + y, **kwargs):
    result = init_value
    for arg in args:
        if type(arg) in (int, float):
            result = op(result, arg)
    for value in kwargs.values():
        if type(value) in (int, float):
            result = op(result, value)
    return result

# 调用calc函数，使用init_value和op的默认值
print(calc(1, 2, 3, x=4, y=5))    # 15
# 调用calc函数，通过lambda函数给op参数赋值
print(calc(1, 2, 3, x=4, y=5, init_value=1, op=lambda x, y: x * y))    # 120
```
> **提示**：注意上面的代码中的`calc`函数，它同时使用了可变参数、关键字参数、命名关键字参数，其中命名关键字参数要放在可变参数和关键字参数之间，传参时先传入可变参数，关键字参数和命名关键字参数的先后顺序并不重要。

有很多函数在Python中用一行代码就能实现，我们可以用Lambda函数来定义这些函数，调用Lambda函数就跟调用普通函数一样，代码如下所示。
```python
import operator, functools

# 一行代码定义求阶乘的函数
fac = lambda num: functools.reduce(operator.mul, range(1, num + 1), 1)
# 一行代码定义判断素数的函数
is_prime = lambda x: x > 1 and all(map(lambda f: x % f, range(2, int(x ** 0.5) + 1)))

# 调用Lambda函数
print(fac(10))        # 3628800
print(is_prime(9))    # False
```
> **提示1**：上面使用的`reduce`函数是Python标准库`functools`模块中的函数，它可以实现对数据的归约操作，通常情况下，**过滤**（filter）、**映射**（map）和**归约**（reduce）是处理数据中非常关键的三个步骤，而Python的标准库也提供了对这三个操作的支持。
> 
> **提示2**：上面使用的`all`函数是Python内置函数，如果传入的序列中所有布尔值都是`True`，`all`函数就返回`True`，否则`all`函数就返回`False`。

### 简单的总结

Python中的函数可以使用可变参数`*args`和关键字参数`**kwargs`来接收任意数量的参数，而且传入参数时可以带上参数名也可以没有参数名，可变参数会被处理成一个元组，而关键字参数会被处理成一个字典。**Python中的函数是一等函数，可以赋值给变量，也可以作为函数的参数和返回值**，这也就意味着我们可以在Python中使用高阶函数。如果我们要定义的函数非常简单，只有一行代码且不需要函数名，可以使用Lambda函数（匿名函数）。

## 函数的高级应用

### 装饰器

装饰器是Python中**用一个函数装饰另外一个函数或类并为其提供额外功能**的语法现象。装饰器本身是一个函数，它的参数是被装饰的函数或类，它的返回值是一个带有装饰功能的函数。很显然，装饰器是一个高阶函数，它的参数和返回值都是函数。下面我们先通过一个简单的例子来说明装饰器的写法和作用，假设已经有名为`downlaod`和`upload`的两个函数，分别用于文件的上传和下载，下面的代码用休眠一段随机时间的方式模拟了下载和上传需要花费的时间，并没有联网做上传下载。

```python
import random
import time

def download(filename):
    print(f'开始下载{filename}.')
    time.sleep(random.randint(2, 6))
    print(f'{filename}下载完成.')

    
def upload(filename):
    print(f'开始上传{filename}.')
    time.sleep(random.randint(4, 8))
    print(f'{filename}上传完成.')

    
download('MySQL从删库到跑路.avi')
upload('Python从入门到住院.pdf')
```
现在我们希望知道调用`download`和`upload`函数做文件上传下载到底用了多少时间，这个应该如何实现呢？相信很多小伙伴已经想到了，我们可以在函数开始执行的时候记录一个时间，在函数调用结束后记录一个时间，两个时间相减就可以计算出下载或上传的时间，代码如下所示。
```python
start = time.time()
download('MySQL从删库到跑路.avi')
end = time.time()
print(f'花费时间: {end - start:.3f}秒')
start = time.time()
upload('Python从入门到住院.pdf')
end = time.time()
print(f'花费时间: {end - start:.3f}秒')
```
通过上面的代码，我们可以得到下载和上传花费的时间，但不知道大家是否注意到，上面记录时间、计算和显示执行时间的代码都是重复代码。有编程经验的人都知道，**重复的代码是万恶之源**，那么有没有办法在不写重复代码的前提下，用一种简单优雅的方式记录下函数的执行时间呢？在Python中，装饰器就是解决这类问题的最佳选择。我们可以把记录函数执行时间的功能封装到一个装饰器中，在有需要的地方直接使用这个装饰器就可以了，代码如下所示。
```python
import time

# 定义装饰器函数，它的参数是被装饰的函数或类
def record_time(func):
    
    # 定义一个带装饰功能（记录被装饰函数的执行时间）的函数
    # 因为不知道被装饰的函数有怎样的参数所以使用*args和**kwargs接收所有参数
    # 在Python中函数可以嵌套的定义（函数中可以再定义函数）
    def wrapper(*args, **kwargs):
        # 在执行被装饰的函数之前记录开始时间
        start = time.time()
        # 执行被装饰的函数并获取返回值
        result = func(*args, **kwargs)
        # 在执行被装饰的函数之后记录结束时间
        end = time.time()
        # 计算和显示被装饰函数的执行时间
        print(f'{func.__name__}执行时间: {end - start:.3f}秒')
        # 返回被装饰函数的返回值（装饰器通常不会改变被装饰函数的执行结果）
        return result
    
    # 返回带装饰功能的wrapper函数
    return wrapper
```
使用上面的装饰器函数有两种方式，第一种方式就是直接调用装饰器函数，传入被装饰的函数并获得返回值，我们可以用这个返回值直接覆盖原来的函数，那么在调用时就已经获得了装饰器提供的额外的功能（记录执行时间），大家可以试试下面的代码就明白了。
```python
download = record_time(download)
upload = record_time(upload)
download('MySQL从删库到跑路.avi')
upload('Python从入门到住院.pdf')
```
上面的代码中已经没有重复代码了，虽然写装饰器会花费一些心思，但是这是一个一劳永逸的骚操作，如果还有其他的函数也需要记录执行时间，按照上面的代码如法炮制即可。

在Python中，使用装饰器很有更为便捷的**语法糖**（编程语言中添加的某种语法，这种语法对语言的功能没有影响，但是使用更加方法，代码的可读性也更强，我们将其称之为“语法糖”或“糖衣语法”），可以用`@装饰器函数`将装饰器函数直接放在被装饰的函数上，效果跟上面的代码相同，下面是完整的代码。
```python
import random
import time

def record_time(func):

    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print(f'{func.__name__}执行时间: {end - start:.3f}秒')
        return result

    return wrapper

@record_time
def download(filename):
    print(f'开始下载{filename}.')
    time.sleep(random.randint(2, 6))
    print(f'{filename}下载完成.')

@record_time
def upload(filename):
    print(f'开始上传{filename}.')
    time.sleep(random.randint(4, 8))
    print(f'{filename}上传完成.')

download('MySQL从删库到跑路.avi')
upload('Python从入门到住院.pdf')
```
上面的代码，我们通过装饰器语法糖为`download`和`upload`函数添加了装饰器，这样调用`download`和`upload`函数时，会记录下函数的执行时间。事实上，被装饰后的`download`和`upload`函数是我们在装饰器`record_time`中返回的`wrapper`函数，调用它们其实就是在调用`wrapper`函数，所以拥有了记录函数执行时间的功能。

如果希望取消装饰器的作用，那么在定义装饰器函数的时候，需要做一些额外的工作。Python标准库`functools`模块的`wraps`函数也是一个装饰器，我们将它放在`wrapper`函数上，这个装饰器可以帮我们保留被装饰之前的函数，这样在需要取消装饰器时，可以通过被装饰函数的`__wrapped__`属性获得被装饰之前的函数。
```python
import random
import time

from functools import wraps

def record_time(func):

    @wraps(func)
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print(f'{func.__name__}执行时间: {end - start:.3f}秒')
        return result

    return wrapper

@record_time
def download(filename):
    print(f'开始下载{filename}.')
    time.sleep(random.randint(2, 6))
    print(f'{filename}下载完成.')

@record_time
def upload(filename):
    print(f'开始上传{filename}.')
    time.sleep(random.randint(4, 8))
    print(f'{filename}上传完成.')

download('MySQL从删库到跑路.avi')
upload('Python从入门到住院.pdf')
# 取消装饰器
download.__wrapped__('MySQL必知必会.pdf')
upload = upload.__wrapped__
upload('Python从新手到大师.pdf')
```
**装饰器函数本身也可以参数化**，简单的说就是通过我们的装饰器也是可以通过调用者传入的参数来定制的，这个知识点我们在后面用到它的时候再为大家讲解。

### 递归调用

Python中允许函数嵌套定义，也允许函数之间相互调用，而且一个函数还可以直接或间接的调用自身。函数自己调用自己称为递归调用，那么递归调用有什么用处呢？现实中，有很多问题的定义本身就是一个递归定义，例如我们之前讲到的阶乘，非负整数`N`的阶乘是`N`乘以`N-1`的阶乘，即N!=N×(N−1)!，定义的左边和右边都出现了阶乘的概念，所以这是一个递归定义。既然如此，我们可以使用递归调用的方式来写一个求阶乘的函数，代码如下所示。

def fac(num):
    if num in (0, 1):
        return 1
    return num * fac(num - 1)

上面的代码中，`fac`函数中又调用了`fac`函数，这就是所谓的递归调用。代码第2行的`if`条件叫做递归的收敛条件，简单的说就是什么时候要结束函数的递归调用，在计算阶乘时，如果计算到`0`或`1`的阶乘，就停止递归调用，直接返回`1`；代码第4行的`num * fac(num - 1)`是递归公式，也就是阶乘的递归定义。下面，我们简单的分析下，如果用`fac(5)`计算`5`的阶乘，整个过程会是怎样的。

### 递归调用函数入栈
```python
# 5 * fac(4)
# 5 * (4 * fac(3))
# 5 * (4 * (3 * fac(2)))
# 5 * (4 * (3 * (2 * fac(1))))
# 停止递归函数出栈
# 5 * (4 * (3 * (2 * 1)))
# 5 * (4 * (3 * 2))
# 5 * (4 * 6)
# 5 * 24
# 120
print(fac(5))    # 120
```
注意，函数调用会通过内存中称为“栈”（stack）的数据结构来保存当前代码的执行现场，函数调用结束后会通过这个栈结构恢复之前的执行现场。栈是一种先进后出的数据结构，这也就意味着最早入栈的函数最后才会返回，而最后入栈的函数会最先返回。例如调用一个名为`a`的函数，函数`a`的执行体中又调用了函数`b`，函数`b`的执行体中又调用了函数`c`，那么最先入栈的函数是`a`，最先出栈的函数是`c`。每进入一个函数调用，栈就会增加一层栈帧（stack frame），栈帧就是我们刚才提到的保存当前代码执行现场的结构；每当函数调用结束后，栈就会减少一层栈帧。通常，内存中的栈空间很小，因此递归调用的次数如果太多，会导致栈溢出（stack overflow），所以**递归调用一定要确保能够快速收敛**。我们可以尝试执行`fac(5000)`，看看是不是会提示`RecursionError`错误，错误消息为：`maximum recursion depth exceeded in comparison`（超出最大递归深度），其实就是发生了栈溢出。

我们使用的Python官方解释器，默认将函数调用的栈结构最大深度设置为`1000`层。如果超出这个深度，就会发生上面说的`RecursionError`。当然，我们可以使用`sys`模块的`setrecursionlimit`函数来改变递归调用的最大深度，例如：`sys.setrecursionlimit(10000)`，这样就可以让上面的`fac(5000)`顺利执行出结果，但是我们不建议这样做，因为让递归快速收敛才是我们应该做的事情，否则就应该考虑使用循环递推而不是递归。

再举一个之前讲过的生成斐波那契数列的例子，因为斐波那契数列前两个数都是`1`，从第3个数开始，每个数是前两个数相加的和，可以记为`f(n) = f(n - 1) + f(n - 2)`，很显然这又是一个递归的定义，所以我们可以用下面的递归调用函数来计算第​`n`个斐波那契数。
```python
def fib(n):
    if n in (1, 2):
        return 1
    return fib(n - 1) + fib(n - 2)

# 打印前20个斐波那契数
for i in range(1, 21):
    print(fib(i))
```
需要提醒大家，上面计算斐波那契数的代码虽然看起来非常简单明了，但执行性能是比较糟糕的，原因大家可以自己思考一下，更好的做法还是之前讲过的使用循环递推的方式，代码如下所示。
```python
def fib(n):
    a, b = 0, 1
    for _ in range(n):
        a, b = b, a + b
    return a
```
### 简单的总结

装饰器是Python中的特色语法，**可以通过装饰器来增强现有的函数**，这是一种非常有用的编程技巧。一些复杂的问题用函数递归调用的方式写起来真的很简单，但是**函数的递归调用一定要注意收敛条件和递归公式**，找到递归公式才有机会使用递归调用，而收敛条件确定了递归什么时候停下来。函数调用通过内存中的栈空间来保存现场和恢复现场，栈空间通常都很小，所以**递归如果不能迅速收敛，很可能会引发栈溢出错误，从而导致程序的崩溃**。


## 面向对象编程入门

面向对象编程是一种非常流行的**编程范式**（programming paradigm），所谓编程范式就是**程序设计的方法论**，简单的说就是程序员对程序的认知和理解以及他们编写代码的方式。

在前面的课程中，我们说过“**程序是指令的集合**”，运行程序时，程序中的语句会变成一条或多条指令，然后由CPU（中央处理器）去执行。为了简化程序的设计，我们又讲到了函数，**把相对独立且经常重复使用的代码放置到函数中**，在需要使用这些代码的时候调用函数即可。如果一个函数的功能过于复杂和臃肿，我们又可以进一步**将函数进一步拆分为多个子函数**来降低系统的复杂性。

不知大家是否发现，我们的编程工作其实是写程序的人按照计算机的工作方式通过代码控制机器完成任务。但是，计算机的工作方式与人类正常的思维模式是不同的，如果编程就必须抛弃人类正常的思维方式去迎合计算机，编程的乐趣就少了很多，而“每个人都应该学习编程”的豪言壮语也就只能喊喊口号而已。这里，我想说的并不是我们不能按照计算机的工作方式去编写代码，但是当我们需要开发一个复杂的系统时，这种方式会让代码过于复杂，从而导致开发和维护工作都变得举步维艰。

随着软件复杂性的增加，编写正确可靠的代码会变成了一项极为艰巨的任务，这也是很多人都坚信“软件开发是人类改造世界所有活动中最为复杂的活动”的原因。如何用程序描述复杂系统和解决复杂问题，就成为了所有程序员必须要思考和直面的问题。诞生于上世纪70年代的Smalltalk语言让软件开发者看到了希望，因为它引入了一种新的编程范式叫面向对象编程。在面向对象编程的世界里，程序中的**数据和操作数据的函数是一个逻辑上的整体**，我们称之为**对象**，**对象可以接收消息**，解决问题的方法就是**创建对象并向对象发出各种各样的消息**；通过消息传递，程序中的多个对象可以协同工作，这样就能构造出复杂的系统并解决现实中的问题。当然，面向对象编程的雏形还可以向前追溯到更早期的Simula语言，但这不是我们现在要讨论的重点。

> **说明：** 今天我们使用的很多高级程序设计语言都支持面向对象编程，但是面向对象编程也不是解决软件开发中所有问题的“银弹”，或者说在软件开发这个行业目前还找不到这种所谓的“银弹”。关于这个问题，大家可以参考IBM360系统之父弗雷德里克·布鲁克斯所发表的论文《没有银弹：软件工程的本质性与附属性工作》或软件工程的经典著作《人月神话》一书。

### 类和对象

如果要用一句话来概括面向对象编程，我认为下面的说法是相当精辟和准确的。

> **面向对象编程**：把一组数据和处理数据的方法组成**对象**，把行为相同的对象归纳为**类**，通过**封装**隐藏对象的内部细节，通过**继承**实现类的特化和泛化，通过**多态**实现基于对象类型的动态分派。

这句话对初学者来说可能不那么容易理解，但是我可以先为大家圈出几个关键词：**对象**（object）、**类**（class）、**封装**（encapsulation）、**继承**（inheritance）、**多态**（polymorphism）。

我们先说说类和对象这两个词。在面向对象编程中，**类是一个抽象的概念，对象是一个具体的概念**。我们把同一类对象的共同特征抽取出来就是一个类，比如我们经常说的人类，这是一个抽象概念，而我们每个人就是人类的这个抽象概念下的实实在在的存在，也就是一个对象。简而言之，**类是对象的蓝图和模板，对象是类的实例，是可以接受消息的实体**。

在面向对象编程的世界中，**一切皆为对象**，**对象都有属性和行为**，**每个对象都是独一无二的**，而且**对象一定属于某个类**。对象的属性是对象的静态特征，对象的行为是对象的动态特征。按照上面的说法，如果我们把拥有共同特征的对象的属性和行为都抽取出来，就可以定义出一个类。

[![](https://github.com/jackfrued/mypic/raw/master/20210731182741.png)](https://github.com/jackfrued/mypic/raw/master/20210731182741.png)

### 定义类

在Python中，可以使用`class`关键字加上类名来定义类，通过缩进我们可以确定类的代码块，就如同定义函数那样。在类的代码块中，我们需要写一些函数，我们说过类是一个抽象概念，那么这些函数就是我们对一类对象共同的动态特征的提取。写在类里面的函数我们通常称之为**方法**，方法就是对象的行为，也就是对象可以接收的消息。**方法的第一个参数通常都是`self`，它代表了接收这个消息的对象本身**。
```python
class Student:

    def study(self, course_name):
        print(f'学生正在学习{course_name}.')

    def play(self):
        print(f'学生正在玩游戏.')
```

### 创建和使用对象

在我们定义好一个类之后，可以使用构造器语法来创建对象，代码如下所示。
```python
stu1 = Student()
stu2 = Student()
print(stu1)    # <__main__.Student object at 0x10ad5ac50>
print(stu2)    # <__main__.Student object at 0x10ad5acd0> 
print(hex(id(stu1)), hex(id(stu2)))    # 0x10ad5ac50 0x10ad5acd0
```

**在类的名字后跟上圆括号就是所谓的构造器语法**，上面的代码创建了两个学生对象，一个赋值给变量`stu1`，一个复制给变量`stu2`。当我们用`print`函数打印`stu1`和`stu2`两个变量时，我们会看到输出了对象在内存中的地址（十六进制形式），跟我们用`id`函数查看对象标识获得的值是相同的。现在我们可以告诉大家，我们定义的变量其实保存的是一个对象在内存中的逻辑地址（位置），通过这个逻辑地址，我们就可以在内存中找到这个对象。所以`stu3 = stu2`这样的赋值语句并没有创建新的对象，只是用一个新的变量保存了已有对象的地址。

接下来，我们尝试给对象发消息，即调用对象的方法。刚才的`Student`类中我们定义了`study`和`play`两个方法，两个方法的第一个参数`self`代表了接收消息的学生对象，`study`方法的第二个参数是学习的课程名称。Python中，给对象发消息有两种方式，请看下面的代码。
```python
# 通过“类.方法”调用方法，第一个参数是接收消息的对象，第二个参数是学习的课程名称
Student.study(stu1, 'Python程序设计')    # 学生正在学习Python程序设计.
# 通过“对象.方法”调用方法，点前面的对象就是接收消息的对象，只需要传入第二个参数
stu1.study('Python程序设计')             # 学生正在学习Python程序设计.

Student.play(stu2)    # 学生正在玩游戏.
stu2.play()           # 学生正在玩游戏. 
```
### 初始化方法

大家可能已经注意到了，刚才我们创建的学生对象只有行为没有属性，如果要给学生对象定义属性，我们可以修改`Student`类，为其添加一个名为`__init__`的方法。**在我们调用`Student`类的构造器创建对象时，首先会在内存中获得保存学生对象所需的内存空间，然后通过自动执行`__init__`方法，完成对内存的初始化操作，也就是把数据放到内存空间中**。所以我们可以通过给`Student`类添加`__init__`方法的方式为学生对象指定属性，同时完成对属性赋初始值的操作，正因如此，`__init__`方法通常也被称为初始化方法。

我们对上面的`Student`类稍作修改，给学生对象添加`name`（姓名）和`age`（年龄）两个属性。
```python
class Student:
    """学生"""

    def __init__(self, name, age):
        """初始化方法"""
        self.name = name
        self.age = age

    def study(self, course_name):
        """学习"""
        print(f'{self.name}正在学习{course_name}.')

    def play(self):
        """玩耍"""
        print(f'{self.name}正在玩游戏.')
```
修改刚才创建对象和给对象发消息的代码，重新执行一次，看看程序的执行结果有什么变化。
```python
# 由于初始化方法除了self之外还有两个参数
# 所以调用Student类的构造器创建对象时要传入这两个参数
stu1 = Student('骆昊', 40)
stu2 = Student('王大锤', 15)
stu1.study('Python程序设计')    # 骆昊正在学习Python程序设计.
stu2.play()                    # 王大锤正在玩游戏.
```
### 打印对象

上面我们通过`__init__`方法在创建对象时为对象绑定了属性并赋予了初始值。在Python中，以**两个下划线`__`（读作“dunder”）开头和结尾的方法通常都是有特殊用途和意义的方法，我们一般称之为魔术方法或魔法方法**。如果我们在打印对象的时候不希望看到对象的地址而是看到我们自定义的信息，可以通过在类中放置`__repr__`魔术方法来做到，该方法返回的字符串就是用`print`函数打印对象的时候会显示的内容，代码如下所示。
```python
class Student:
    """学生"""

    def __init__(self, name, age):
        """初始化方法"""
        self.name = name
        self.age = age

    def study(self, course_name):
        """学习"""
        print(f'{self.name}正在学习{course_name}.')

    def play(self):
        """玩耍"""
        print(f'{self.name}正在玩游戏.')
    
    def __repr__(self):
        return f'{self.name}: {self.age}'

stu1 = Student('骆昊', 40)
print(stu1)        # 骆昊: 40
students = [stu1, Student('李元芳', 36), Student('王大锤', 25)]
print(students)    # [骆昊: 40, 李元芳: 36, 王大锤: 25]
```
### 面向对象的支柱

面向对象编程有三大支柱，**封装**、**继承**和**多态**。

我自己对封装的理解是：**隐藏一切可以隐藏的实现细节，只向外界暴露简单的调用接口**。我们在类中定义的对象方法其实就是一种封装，这种封装可以让我们在创建对象之后，只需要给对象发送一个消息就可以执行方法中的代码，也就是说我们在只知道方法的名字和参数（方法的外部视图），不知道方法内部实现细节（方法的内部视图）的情况下就完成了对方法的使用。

在很多场景下，面向对象编程其实就是一个三步走的问题。第一步定义类，第二步创建对象，第三步给对象发消息。当然，有的时候我们是不需要第一步的，因为我们想用的类可能已经存在了。之前我们说过，Python内置的`list`、`set`、`dict`其实都不是函数而是类，如果要创建列表、集合、字典对象，我们就不用自定义类了。当然，有的类并不是Python标准库中直接提供的，它可能来自于第三方的代码，如何安装和使用三方代码在后续课程中会进行讨论。在某些特殊的场景中，我们会用到名为“内置对象”的对象，所谓“内置对象”就是说上面三步走的第一步和第二步都不需要了，因为类已经存在而且对象已然创建过了，直接向对象发消息就可以了，这也就是我们常说的“开箱即用”。



### 简单的总结

面向对象编程是一种非常流行的编程范式，除此之外还有**指令式编程**、**函数式编程**等编程范式。由于现实世界是由对象构成的，而对象是可以接收消息的实体，所以**面向对象编程更符合人类正常的思维习惯**。类是抽象的，对象是具体的，有了类就能创建对象，有了对象就可以接收消息，这就是面向对象编程的基础。定义类的过程是一个抽象的过程，找到对象公共的属性属于数据抽象，找到对象公共的方法属于行为抽象。抽象的过程是一个仁者见仁智者见智的过程，对同一类对象进行抽象可能会得到不同的结果，如下图所示。

[![](https://github.com/jackfrued/mypic/raw/master/20210731182914.png)](https://github.com/jackfrued/mypic/raw/master/20210731182914.png)

> **说明：** 本节课的插图来自于 Grady Booc 等撰写的《面向对象分析与设计》一书，该书是讲解面向对象编程的经典著作，有兴趣的读者可以购买和阅读这本书来了解更多的面向对象的相关知识。


### 可见性和属性装饰器

在很多面向对象编程语言中，对象的属性通常会被设置为私有（private）或受保护（protected）的成员，简单的说就是不允许直接访问这些属性；对象的方法通常都是公开的（public），因为公开的方法是对象能够接受的消息，也是对象暴露给外界的调用接口，这就是所谓的访问可见性。在Python中，可以通过给对象属性名添加前缀下划线的方式来说明属性的访问可见性，例如，**可以用`__name`表示一个私有属性，`_name`表示一个受保护属性**。

```python
class Student:

    def __init__(self, name, age):
        self.__name = name
        self.__age = age

    def study(self, course_name):
        print(f'{self.__name}正在学习{course_name}.')

stu = Student('王大锤', 20)
stu.study('Python程序设计')
print(stu.__name)
```

上面代码的最后一行会引发`AttributeError`（属性错误）异常，异常消息为：`'Student' object has no attribute '__name'`。由此可见，以`__`开头的属性`__name`是私有的，在类的外面无法直接访问，但是类里面的`study`方法中可以通过`self.__name`访问该属性。

需要提醒大家的是，Python并没有从语法上严格保证私有属性的私密性，它只是给私有的属性和方法换了一个名字来阻挠对它们的访问，事实上如果你知道更换名字的规则仍然可以访问到它们，我们可以对上面的代码稍作修改就可以访问到私有的属性。
```python
class Student:

    def __init__(self, name, age):
        self.__name = name
        self.__age = age

    def study(self, course_name):
        print(f'{self.__name}正在学习{course_name}.')

stu = Student('王大锤', 20)
stu.study('Python程序设计')
print(stu._Student__name, stu._Student__age)
```

Python中有一句名言：“**We are all consenting adults here**”（大家都是成年人）。Python语言的设计者认为程序员要为自己的行为负责，而不是由Python语言本身来严格限制访问可见性，而大多数的程序员都认为**开放比封闭要好**，把对象的属性私有化并不是编程语言必须的东西，所以Python并没有从语法上做出最严格的限定。

Python中可以通过`property`装饰器为“私有”属性提供读取和修改的方法，之前我们提到过，装饰器通常会放在类、函数或方法的声明之前，通过一个`@`符号表示将装饰器应用于类、函数或方法。
```python
class Student:

    def __init__(self, name, age):
        self.__name = name
        self.__age = age

    # 属性访问器(getter方法) - 获取__name属性
    @property
    def name(self):
        return self.__name
    
    # 属性修改器(setter方法) - 修改__name属性
    @name.setter
    def name(self, name):
        # 如果name参数不为空就赋值给对象的__name属性
        # 否则将__name属性赋值为'无名氏'，有两种写法
        # self.__name = name if name else '无名氏'
        self.__name = name or '无名氏'
    
    @property
    def age(self):
        return self.__age

stu = Student('王大锤', 20)
print(stu.name, stu.age)    # 王大锤 20
stu.name = ''
print(stu.name)    # 无名氏
# stu.age = 30     # AttributeError: can't set attribute
```

在实际项目开发中，我们并不经常使用私有属性，属性装饰器的使用也比较少，所以上面的知识点大家简单了解一下就可以了。

### 动态属性

Python是一门动态语言，维基百科对动态语言的解释是：“在运行时可以改变其结构的语言，例如新的函数、对象、甚至代码可以被引进，已有的函数可以被删除或是其他结构上的变化。动态语言非常灵活，目前流行的Python和JavaScript都是动态语言，除此之外如PHP、Ruby等也都属于动态语言，而C、C++等语言则不属于动态语言”。

在Python中，我们可以动态为对象添加属性，这是Python作为动态类型语言的一项特权，代码如下所示。需要提醒大家的是，对象的方法其实本质上也是对象的属性，如果给对象发送一个无法接收的消息，引发的异常仍然是`AttributeError`。
```python
class Student:

    def __init__(self, name, age):
        self.name = name
        self.age = age

stu = Student('王大锤', 20)
# 为Student对象动态添加sex属性
stu.sex = '男'
```
如果不希望在使用对象时动态的为对象添加属性，可以使用Python的`__slots__`魔法。对于`Student`类来说，可以在类中指定`__slots__ = ('name', 'age')`，这样`Student`类的对象只能有`name`和`age`属性，如果想动态添加其他属性将会引发异常，代码如下所示。
```python
class Student:
    __slots__ = ('name', 'age')

    def __init__(self, name, age):
        self.name = name
        self.age = age

stu = Student('王大锤', 20)
# AttributeError: 'Student' object has no attribute 'sex'
stu.sex = '男'
```
### 静态方法和类方法

**之前我们在类中定义的方法都是对象方法，换句话说这些方法都是对象可以接收的消息。除了对象方法之外，类中还可以有静态方法和类方法，这两类方法是发给类的消息，二者并没有实质性的区别。在面向对象的世界里，一切皆为对象，我们定义的每一个类其实也是一个对象，而静态方法和类方法就是发送给类对象的消息**。那么，什么样的消息会直接发送给类对象呢？

举一个例子，定义一个三角形类，通过传入三条边的长度来构造三角形，并提供计算周长和面积的方法。计算周长和面积肯定是三角形对象的方法，这一点毫无疑问。但是在创建三角形对象时，传入的三条边长未必能构造出三角形，为此我们可以先写一个方法来验证给定的三条边长是否可以构成三角形，这种方法很显然就不是对象方法，因为在调用这个方法时三角形对象还没有创建出来。我们可以把这类方法设计为静态方法或类方法，也就是说这类方法不是发送给三角形对象的消息，而是发送给三角形类的消息，代码如下所示。
```python
class Triangle(object):
    """三角形类"""

    def __init__(self, a, b, c):
        """初始化方法"""
        self.a = a
        self.b = b
        self.c = c

    @staticmethod
    def is_valid(a, b, c):
        """判断三条边长能否构成三角形(静态方法)"""
        return a + b > c and b + c > a and a + c > b

    # @classmethod
    # def is_valid(cls, a, b, c):
    #     """判断三条边长能否构成三角形(类方法)"""
    #     return a + b > c and b + c > a and a + c > b

    def perimeter(self):
        """计算周长"""
        return self.a + self.b + self.c

    def area(self):
        """计算面积"""
        p = self.perimeter() / 2
        return (p * (p - self.a) * (p - self.b) * (p - self.c)) ** 0.5
```
上面的代码使用`staticmethod`装饰器声明了`is_valid`方法是`Triangle`类的静态方法，如果要声明类方法，可以使用`classmethod`装饰器。可以直接使用`类名.方法名`的方式来调用静态方法和类方法，二者的区别在于，类方法的第一个参数是类对象本身，而静态方法则没有这个参数。简单的总结一下，**对象方法、类方法、静态方法都可以通过`类名.方法名`的方式来调用，区别在于方法的第一个参数到底是普通对象还是类对象，还是没有接受消息的对象**。静态方法通常也可以直接写成一个独立的函数，因为它并没有跟特定的对象绑定。

### 继承和多态

```python
class Person:
    """人类"""

    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def eat(self):
        print(f'{self.name}正在吃饭.')
    
    def sleep(self):
        print(f'{self.name}正在睡觉.')

class Student(Person):
    """学生类"""
    
    def __init__(self, name, age):
        # super(Student, self).__init__(name, age)
        super().__init__(name, age)
    
    def study(self, course_name):
        print(f'{self.name}正在学习{course_name}.')

class Teacher(Person):
    """老师类"""

    def __init__(self, name, age, title):
        # super(Teacher, self).__init__(name, age)
        super().__init__(name, age)
        self.title = title
    
    def teach(self, course_name):
        print(f'{self.name}{self.title}正在讲授{course_name}.')

stu1 = Student('白元芳', 21)
stu2 = Student('狄仁杰', 22)
teacher = Teacher('武则天', 35, '副教授')
stu1.eat()
stu2.sleep()
teacher.teach('Python程序设计')
stu1.study('Python程序设计')
```
继承的语法是在定义类的时候，在类名后的圆括号中指定当前类的父类。如果定义一个类的时候没有指定它的父类是谁，那么默认的父类是`object`类。`object`类是Python中的顶级类，这也就意味着所有的类都是它的子类，要么直接继承它，要么间接继承它。Python语言允许多重继承，也就是说一个类可以有一个或多个父类，关于多重继承的问题我们在后面会有更为详细的讨论。在子类的初始化方法中，我们可以通过`super().__init__()`来调用父类初始化方法，`super`函数是Python内置函数中专门为获取当前对象的父类对象而设计的。从上面的代码可以看出，子类除了可以通过继承得到父类提供的属性和方法外，还可以定义自己特有的属性和方法，所以子类比父类拥有的更多的能力。在实际开发中，我们经常会用子类对象去替换掉一个父类对象，这是面向对象编程中一个常见的行为，也叫做“里氏替换原则”（Liskov Substitution Principle）。
。

### 简单的总结

Python是动态语言，Python中的对象可以动态的添加属性。在面向对象的世界中，**一切皆为对象**，我们定义的类也是对象，所以**类也可以接收消息**，对应的方法是类方法或静态方法。通过继承，我们**可以从已有的类创建新类**，实现对已有类代码的复用。


## Python标准库初探

### base64 - Base64编解码模块

**Base64**是一种基于64个可打印字符来表示二进制数据的方法。由于$log _{2}64=6$，所以Base64以6个比特（二进制位，可以表示0或1）为一个单元，每个单元对应一个可打印字符。对于3字节（24比特）的二进制数据，我们可以将其处理成对应于4个Base64单元，即3个字节可由4个可打印字符来表示。Base64编码可用来作为电子邮件的传输编码，也可以用于其他需要将二进制数据转成文本字符的场景，这使得在XML、JSON、YAML这些文本数据格式中传输二进制内容成为可能。在Base64中的可打印字符包括`A-Z`、`a-z`、`0-9`，这里一共是62个字符，另外两个可打印符号通常是`+`和`/`，`=`用于在Base64编码最后进行补位。

关于Base64编码的细节，大家可以参考[《Base64笔记》](http://www.ruanyifeng.com/blog/2008/06/base64.html)一文，Python标准库中的`base64`模块提供了`b64encode`和`b64decode`两个函数，专门用于实现Base64的编码和解码，下面演示了在**Python的交互式环境**中执行这两个函数的效果。

```Python
>>> import base64
>>> 
>>> content = 'Man is distinguished, not only by his reason, but by this singular passion from other animals, which is a lust of the mind, that by a perseverance of delight in the continued and indefatigable generation of knowledge, exceeds the short vehemence of any carnal pleasure.'
>>> base64.b64encode(content.encode())
b'TWFuIGlzIGRpc3Rpbmd1aXNoZWQsIG5vdCBvbmx5IGJ5IGhpcyByZWFzb24sIGJ1dCBieSB0aGlzIHNpbmd1bGFyIHBhc3Npb24gZnJvbSBvdGhlciBhbmltYWxzLCB3aGljaCBpcyBhIGx1c3Qgb2YgdGhlIG1pbmQsIHRoYXQgYnkgYSBwZXJzZXZlcmFuY2Ugb2YgZGVsaWdodCBpbiB0aGUgY29udGludWVkIGFuZCBpbmRlZmF0aWdhYmxlIGdlbmVyYXRpb24gb2Yga25vd2xlZGdlLCBleGNlZWRzIHRoZSBzaG9ydCB2ZWhlbWVuY2Ugb2YgYW55IGNhcm5hbCBwbGVhc3VyZS4='
>>> content = b'TWFuIGlzIGRpc3Rpbmd1aXNoZWQsIG5vdCBvbmx5IGJ5IGhpcyByZWFzb24sIGJ1dCBieSB0aGlzIHNpbmd1bGFyIHBhc3Npb24gZnJvbSBvdGhlciBhbmltYWxzLCB3aGljaCBpcyBhIGx1c3Qgb2YgdGhlIG1pbmQsIHRoYXQgYnkgYSBwZXJzZXZlcmFuY2Ugb2YgZGVsaWdodCBpbiB0aGUgY29udGludWVkIGFuZCBpbmRlZmF0aWdhYmxlIGdlbmVyYXRpb24gb2Yga25vd2xlZGdlLCBleGNlZWRzIHRoZSBzaG9ydCB2ZWhlbWVuY2Ugb2YgYW55IGNhcm5hbCBwbGVhc3VyZS4='
>>> base64.b64decode(content).decode()
'Man is distinguished, not only by his reason, but by this singular passion from other animals, which is a lust of the mind, that by a perseverance of delight in the continued and indefatigable generation of knowledge, exceeds the short vehemence of any carnal pleasure.'
```

### collections - 容器数据类型模块

`collections`模块提供了诸多非常好用的数据结构，主要包括：

- `namedtuple`：命令元组，它是一个类工厂，接受类型的名称和属性列表来创建一个类。
- `deque`：双端队列，是列表的替代实现。Python中的列表底层是基于数组来实现的，而`deque`底层是双向链表，因此当你需要在头尾添加和删除元素是，`deque`会表现出更好的性能，渐近时间复杂度为$O(1)$。
- `Counter`：`dict`的子类，键是元素，值是元素的计数，它的`most_common()`方法可以帮助我们获取出现频率最高的元素。`Counter`和`dict`的继承关系我认为是值得商榷的，按照CARP原则，`Counter`跟`dict`的关系应该设计为关联关系更为合理。
- `OrderedDict`：`dict`的子类，它记录了键值对插入的顺序，看起来既有字典的行为，也有链表的行为。
- `defaultdict`：类似于字典类型，但是可以通过默认的工厂函数来获得键对应的默认值，相比字典中的`setdefault()`方法，这种做法更加高效。

下面是在**Python交互式环境中**使用`namedtuple`创建扑克牌类的例子。

```Python
>>> from collections import namedtuple
>>>
>>> Card = namedtuple('Card', ('suite', 'face'))
>>> card1 = Card('红桃', 5)
>>> card2 = Card('草花', 9)
>>> card1
Card(suite='红桃', face=5)
>>> card2
Card(suite='草花', face=9)
>>> print(f'{card1.suite}{card1.face}')
红桃5
>>> print(f'{card2.suite}{card2.face}')
草花9
```

下面是使用`Counter`类统计列表中出现次数最多的三个元素的例子。

```Python
from collections import Counter

words = [
    'look', 'into', 'my', 'eyes', 'look', 'into', 'my', 'eyes',
    'the', 'eyes', 'the', 'eyes', 'the', 'eyes', 'not', 'around',
    'the', 'eyes', "don't", 'look', 'around', 'the', 'eyes',
    'look', 'into', 'my', 'eyes', "you're", 'under'
]
counter = Counter(words)
# 打印words列表中出现频率最高的3个元素及其出现次数
for elem, count in counter.most_common(3):
    print(elem, count)
```

### hashlib - 哈希函数模块

哈希函数又称哈希算法或散列函数，是一种为已有的数据创建“数字指纹”（哈希摘要）的方法。哈希函数把数据压缩成摘要，对于相同的输入，哈希函数可以生成相同的摘要（数字指纹），需要注意的是这个过程并不可逆（不能通过摘要计算出输入的内容）。一个优质的哈希函数能够为不同的输入生成不同的摘要，出现哈希冲突（不同的输入产生相同的摘要）的概率极低，[MD5](https://zh.wikipedia.org/wiki/MD5)、[SHA家族]([https://zh.wikipedia.org/wiki/SHA%E5%AE%B6%E6%97%8F](https://zh.wikipedia.org/wiki/SHA家族))就是这类好的哈希函数。

> **说明**：在2011年的时候，RFC 6151中已经禁止将MD5用作密钥散列消息认证码，这个问题不在我们讨论的范围内。

Python标准库的`hashlib`模块提供了对哈希函数的封装，通过使用`md5`、`sha1`、`sha256`等类，我们可以轻松的生成“数字指纹”。举一个简单的例子，用户注册时我们希望在数据库中保存用户的密码，很显然我们不能将用户密码直接保存在数据库中，这样可能会导致用户隐私的泄露，所以在数据库中保存用户密码时，通常都会将密码的“指纹”保存起来，用户登录时通过哈希函数计算密码的“指纹”再进行匹配来判断用户登录是否成功。

```Python
import hashlib

# 计算字符串"123456"的MD5摘要
print(hashlib.md5('123456'.encode()).hexdigest())

# 计算文件"Python-3.7.1.tar.xz"的MD5摘要
hasher = hashlib.md5()
with open('Python-3.7.1.tar.xz', 'rb') as file:
    data = file.read(512)
    while data:
        hasher.update(data)
        data = file.read(512)
print(hasher.hexdigest())
```

> **说明**：很多网站在下载链接的旁边都提供了哈希摘要，完成文件下载后，我们可以计算该文件的哈希摘要并检查它与网站上提供的哈希摘要是否一致（指纹比对）。如果计算出的哈希摘要与网站提供的并不一致，很有可能是下载出错或该文件在传输过程中已经被篡改，这时候就不应该直接使用这个文件。

### heapq - 堆排序模块

`heapq`模块实现了堆排序算法，如果希望使用堆排序，尤其是要解决**TopK问题**（从序列中找到K个最大或最小元素），直接使用该模块即可，代码如下所示。

```Python
import heapq

list1 = [34, 25, 12, 99, 87, 63, 58, 78, 88, 92]
# 找出列表中最大的三个元素
print(heapq.nlargest(3, list1))
# 找出列表中最小的三个元素
print(heapq.nsmallest(3, list1))

list2 = [
    {'name': 'IBM', 'shares': 100, 'price': 91.1},
    {'name': 'AAPL', 'shares': 50, 'price': 543.22},
    {'name': 'FB', 'shares': 200, 'price': 21.09},
    {'name': 'HPQ', 'shares': 35, 'price': 31.75},
    {'name': 'YHOO', 'shares': 45, 'price': 16.35},
    {'name': 'ACME', 'shares': 75, 'price': 115.65}
]
# 找出价格最高的三只股票
print(heapq.nlargest(3, list2, key=lambda x: x['price']))
# 找出持有数量最高的三只股票
print(heapq.nlargest(3, list2, key=lambda x: x['shares']))
```

### itertools - 迭代工具模块

`itertools`可以帮助我们生成各种各样的迭代器，大家可以看看下面的例子。

```Python
import itertools

# 产生ABCD的全排列
for value in itertools.permutations('ABCD'):
    print(value)

# 产生ABCDE的五选三组合
for value in itertools.combinations('ABCDE', 3):
    print(value)

# 产生ABCD和123的笛卡尔积
for value in itertools.product('ABCD', '123'):
    print(value)

# 产生ABC的无限循环序列
it = itertools.cycle(('A', 'B', 'C'))
print(next(it))
print(next(it))
print(next(it))
print(next(it))
```

### random - 随机数和随机抽样模块

这个模块我们之前已经用过很多次了，生成随机数、实现随机乱序和随机抽样，下面是常用函数的列表。

- `getrandbits(k)`：返回具有`k`个随机比特位的整数。
- `randrange(start, stop[, step])`：从`range(start, stop, step)` 返回一个随机选择的元素，但实际上并没有构建一个`range`对象。
- `randint(a, b)`：返回随机整数`N`满足`a <= N <= b`，相当于`randrange(a, b+1)`。
- `choice(seq)`：从非空序列`seq`返回一个随机元素。 如果`seq`为空，则引发`IndexError`。
- `choices(population, weight=None, *, cum_weights=None, k=1)`：从`population`中选择替换，返回大小为`k`的元素列表。 如果`population`为空，则引发`IndexError`。
- `shuffle(x[, random])`：将序列`x`随机打乱位置。
- `sample(population, k)`：返回从总体序列或集合中选择`k`个不重复元素构造的列表，用于无重复的随机抽样。
- `random()`：返回`[0.0, 1.0)`范围内的下一个随机浮点数。
- `expovariate(lambd)`：指数分布。
- `gammavariate(alpha, beta)`：伽玛分布。
- `gauss(mu, sigma)` / `normalvariate(mu, sigma)`：正态分布。
- `paretovariate(alpha)`：帕累托分布。 
- `weibullvariate(alpha, beta)`：威布尔分布。

### os.path - 路径操作相关模块

`os.path`模块封装了操作路径的工具函数，如果程序中需要对文件路径做拼接、拆分、获取以及获取文件的存在性和其他属性，这个模块将会非常有帮助，下面为大家罗列一些常用的函数。

- `dirname(path)`：返回路径`path`的目录名称。
- `exists(path)`：如果`path`指向一个已存在的路径或已打开的文件描述符，返回 `True`。
- `getatime(path)` / `getmtime(path)` / `getctime(path)`：返回`path`的最后访问时间/最后修改时间/创建时间。
- `getsize(path)`：返回`path`的大小，以字节为单位。如果该文件不存在或不可访问，则抛出`OSError`异常。
- `isfile(path)`：如果`path`是普通文件，则返回 `True`。
- `isdir(path)`：如果`path`是目录（文件夹），则返回`True`。
- `join(path, *paths)`：合理地拼接一个或多个路径部分。返回值是`path`和`paths`所有值的连接，每个非空部分后面都紧跟一个目录分隔符 (`os.sep`)，除了最后一部分。这意味着如果最后一部分为空，则结果将以分隔符结尾。如果参数中某个部分是绝对路径，则绝对路径前的路径都将被丢弃，并从绝对路径部分开始连接。
- `splitext(path)`：将路径`path`拆分为一对，即`(root, ext)`，使得`root + ext == path`，其中`ext`为空或以英文句点开头，且最多包含一个句点。

### uuid - UUID生成模块

`uuid`模块可以帮助我们生成全局唯一标识符（Universal Unique IDentity）。该模块提供了四个用于生成UUID的函数，分别是：

- `uuid1()`：由MAC地址、当前时间戳、随机数生成，可以保证全球范围内的唯一性。
- `uuid3(namespace, name)`：通过计算命名空间和名字的MD5哈希摘要（“指纹”）值得到，保证了同一命名空间中不同名字的唯一性，和不同命名空间的唯一性，但同一命名空间的同一名字会生成相同的UUID。
- `uuid4()`：由伪随机数生成UUID，有一定的重复概率，该概率可以计算出来。
- `uuid5()`：算法与`uuid3`相同，只不过哈希函数用SHA-1取代了MD5。

由于`uuid4`存在概率型重复，那么在真正需要全局唯一标识符的地方最好不用使用它。在分布式环境下，`uuid1`是很好的选择，因为它能够保证生成ID的全局唯一性。下面是在**Python交互式环境中**使用`uuid1`函数生成全局唯一标识符的例子。

```Python
>>> import uuid
>>> uuid.uuid1().hex
'622a8334baab11eaaa9c60f81da8d840'
>>> uuid.uuid1().hex
'62b066debaab11eaaa9c60f81da8d840'
>>> uuid.uuid1().hex
'642c0db0baab11eaaa9c60f81da8d840'
```

## 文件读写和异常处理

实际开发中常常会遇到对数据进行持久化的场景，所谓持久化是指将数据从无法长久保存数据的存储介质（通常是内存）转移到可以长久保存数据的存储介质（通常是硬盘）中。实现数据持久化最直接简单的方式就是通过**文件系统**将数据保存到**文件**中。

计算机的**文件系统**是一种存储和组织计算机数据的方法，它使得对数据的访问和查找变得容易，文件系统使用**文件**和**树形目录**的抽象逻辑概念代替了硬盘、光盘、闪存等物理设备的数据块概念，用户使用文件系统来保存数据时，不必关心数据实际保存在硬盘的哪个数据块上，只需要记住这个文件的路径和文件名。在写入新数据之前，用户不必关心硬盘上的哪个数据块没有被使用，硬盘上的存储空间管理（分配和释放）功能由文件系统自动完成，用户只需要记住数据被写入到了哪个文件中。

### 打开和关闭文件

有了文件系统，我们可以非常方便的通过文件来读写数据；在Python中要实现文件操作是非常简单的。我们可以使用Python内置的`open`函数来打开文件，在使用`open`函数时，我们可以通过函数的参数指定**文件名**、**操作模式**和**字符编码**等信息，接下来就可以对文件进行读写操作了。这里所说的操作模式是指要打开什么样的文件（字符文件或二进制文件）以及做什么样的操作（读、写或追加），具体如下表所示。

| 操作模式 | 具体含义                         |
| -------- | -------------------------------- |
| `'r'`    | 读取 （默认）                    |
| `'w'`    | 写入（会先截断之前的内容）       |
| `'x'`    | 写入，如果文件已经存在会产生异常 |
| `'a'`    | 追加，将内容写入到已有文件的末尾 |
| `'b'`    | 二进制模式                       |
| `'t'`    | 文本模式（默认）                 |
| `'+'`    | 更新（既可以读又可以写）         |

下图展示了如何根据程序的需要来设置`open`函数的操作模式。

<img src="https://github.com/jackfrued/mypic/raw/master/20210803201644.png" width="75%">

在使用`open`函数时，如果打开的文件是字符文件（文本文件），可以通过`encoding`参数来指定读写文件使用的字符编码。如果对字符编码和字符集这些概念不了解，可以看看[《字符集和字符编码》](https://www.cnblogs.com/skynet/archive/2011/05/03/2035105.html)一文，此处不再进行赘述。

使用`open`函数打开文件成功后会返回一个文件对象，通过这个对象，我们就可以实现对文件的读写操作；如果打开文件失败，`open`函数会引发异常，稍后会对此加以说明。如果要关闭打开的文件，可以使用文件对象的`close`方法，这样可以在结束文件操作时释放掉这个文件。

### 读写文本文件

用`open`函数打开文本文件时，需要指定文件名并将文件的操作模式设置为`'r'`，如果不指定，默认值也是`'r'`；如果需要指定字符编码，可以传入`encoding`参数，如果不指定，默认值是None，那么在读取文件时使用的是操作系统默认的编码。需要提醒大家，如果不能保证保存文件时使用的编码方式与`encoding`参数指定的编码方式是一致的，那么就可能因无法解码字符而导致读取文件失败。

下面的例子演示了如何读取一个纯文本文件（一般指只有字符原生编码构成的文件，与富文本相比，纯文本不包含字符样式的控制元素，能够被最简单的文本编辑器直接读取）。

```Python
file = open('致橡树.txt', 'r', encoding='utf-8')
print(file.read())
file.close()
```

> **说明**：[《致橡树》](http://www.china.org.cn/learning_english/2011-02/21/content_21967654.htm)是舒婷老师在1977年3月创建的爱情诗，也是我最喜欢的现代诗之一。

除了使用文件对象的`read`方法读取文件之外，还可以使用`for-in`循环逐行读取或者用`readlines`方法将文件按行读取到一个列表容器中，代码如下所示。

```Python
file = open('致橡树.txt', 'r', encoding='utf-8')
for line in file:
    print(line, end='')
file.close()

file = open('致橡树.txt', 'r', encoding='utf-8')
lines = file.readlines()
for line in lines:
    print(line, end='')
file.close()
```

如果要向文件中写入内容，可以在打开文件时使用`w`或者`a`作为操作模式，前者会截断之前的文本内容写入新的内容，后者是在原来内容的尾部追加新的内容。

```Python
file = open('致橡树.txt', 'a', encoding='utf-8')
file.write('\n标题：《致橡树》')
file.write('\n作者：舒婷')
file.write('\n时间：1977年3月')
file.close()
```

### 异常处理机制

请注意上面的代码，如果`open`函数指定的文件并不存在或者无法打开，那么将引发异常状况导致程序崩溃。为了让代码具有健壮性和容错性，我们可以**使用Python的异常机制对可能在运行时发生状况的代码进行适当的处理**。Python中和异常相关的关键字有五个，分别是`try`、`except`、`else`、`finally`和`raise`，我们先看看下面的代码，再来为大家介绍这些关键字的用法。

```Python
file = None
try:
    file = open('致橡树.txt', 'r', encoding='utf-8')
    print(file.read())
except FileNotFoundError:
    print('无法打开指定的文件!')
except LookupError:
    print('指定了未知的编码!')
except UnicodeDecodeError:
    print('读取文件时解码错误!')
finally:
    if file:
        file.close()
```

在Python中，我们可以将运行时会出现状况的代码放在`try`代码块中，在`try`后面可以跟上一个或多个`except`块来捕获异常并进行相应的处理。例如，在上面的代码中，文件找不到会引发`FileNotFoundError`，指定了未知的编码会引发`LookupError`，而如果读取文件时无法按指定编码方式解码文件会引发`UnicodeDecodeError`，所以我们在`try`后面跟上了三个`except`分别处理这三种不同的异常状况。在`except`后面，我们还可以加上`else`代码块，这是`try` 中的代码没有出现异常时会执行的代码，而且`else`中的代码不会再进行异常捕获，也就是说如果遇到异常状况，程序会因异常而终止并报告异常信息。最后我们使用`finally`代码块来关闭打开的文件，释放掉程序中获取的外部资源。由于`finally`块的代码不论程序正常还是异常都会执行，甚至是调用了`sys`模块的`exit`函数终止Python程序，`finally`块中的代码仍然会被执行（因为`exit`函数的本质是引发了`SystemExit`异常），因此我们把**`finally`代码块称为“总是执行代码块**”，它最适合用来做释放外部资源的操作。

Python中内置了大量的异常类型，除了上面代码中用到的异常类型以及之前的课程中遇到过的异常类型外，还有许多的异常类型，其继承结构如下所示。

```
BaseException
 +-- SystemExit
 +-- KeyboardInterrupt
 +-- GeneratorExit
 +-- Exception
      +-- StopIteration
      +-- StopAsyncIteration
      +-- ArithmeticError
      |    +-- FloatingPointError
      |    +-- OverflowError
      |    +-- ZeroDivisionError
      +-- AssertionError
      +-- AttributeError
      +-- BufferError
      +-- EOFError
      +-- ImportError
      |    +-- ModuleNotFoundError
      +-- LookupError
      |    +-- IndexError
      |    +-- KeyError
      +-- MemoryError
      +-- NameError
      |    +-- UnboundLocalError
      +-- OSError
      |    +-- BlockingIOError
      |    +-- ChildProcessError
      |    +-- ConnectionError
      |    |    +-- BrokenPipeError
      |    |    +-- ConnectionAbortedError
      |    |    +-- ConnectionRefusedError
      |    |    +-- ConnectionResetError
      |    +-- FileExistsError
      |    +-- FileNotFoundError
      |    +-- InterruptedError
      |    +-- IsADirectoryError
      |    +-- NotADirectoryError
      |    +-- PermissionError
      |    +-- ProcessLookupError
      |    +-- TimeoutError
      +-- ReferenceError
      +-- RuntimeError
      |    +-- NotImplementedError
      |    +-- RecursionError
      +-- SyntaxError
      |    +-- IndentationError
      |         +-- TabError
      +-- SystemError
      +-- TypeError
      +-- ValueError
      |    +-- UnicodeError
      |         +-- UnicodeDecodeError
      |         +-- UnicodeEncodeError
      |         +-- UnicodeTranslateError
      +-- Warning
           +-- DeprecationWarning
           +-- PendingDeprecationWarning
           +-- RuntimeWarning
           +-- SyntaxWarning
           +-- UserWarning
           +-- FutureWarning
           +-- ImportWarning
           +-- UnicodeWarning
           +-- BytesWarning
           +-- ResourceWarning
```

从上面的继承结构可以看出，Python中所有的异常都是`BaseException`的子类型，它有四个直接的子类，分别是：`SystemExit`、`KeyboardInterrupt`、`GeneratorExit`和`Exception`。其中，`SystemExit`表示解释器请求退出，`KeyboardInterrupt`是用户中断程序执行（按下`Ctrl+c`），`GeneratorExit`表示生成器发生异常通知退出，不理解这些异常没有关系，继续学习就好了。值得一提的是`Exception`类，它是常规异常类型的父类型，很多的异常都是直接或间接的继承自`Exception`类。如果Python内置的异常类型不能满足应用程序的需要，我们可以自定义异常类型，而自定义的异常类型也应该直接或间接继承自`Exception`类，当然还可以根据需要重写或添加方法。

在Python中，可以使用`raise`关键字来引发异常（抛出异常对象），而调用者可以通过`try...except...`结构来捕获并处理异常。例如在函数中，当函数的执行条件不满足时，可以使用抛出异常的方式来告知调用者问题的所在，而调用者可以通过捕获处理异常来使得代码从异常中恢复，定义异常和抛出异常的代码如下所示。

```Python
class InputError(ValueError):
    """自定义异常类型"""
    pass


def fac(num):
    """求阶乘"""
    if num < 0:
        raise InputError('只能计算非负整数的阶乘')
    if num in (0, 1):
        return 1
    return num * fac(num - 1)
```

调用求阶乘的函数`fac`，通过`try...except...`结构捕获输入错误的异常并打印异常对象（显示异常信息），如果输入正确就计算阶乘并结束程序。

```Python
flag = True
while flag:
    num = int(input('n = '))
    try:
        print(f'{num}! = {fac(num)}')
        flag = False
    except InputError as err:
        print(err)
```

### 上下文语法

对于`open`函数返回的文件对象，还可以使用`with`上下文语法在文件操作完成后自动执行文件对象的`close`方法，这样可以让代码变得更加简单优雅，因为不需要再写`finally`代码块来执行关闭文件释放资源的操作。需要提醒大家的是，并不是所有的对象都可以放在`with`上下文语法中，只有符合**上下文管理器协议**（有`__enter__`和`__exit__`魔术方法）的对象才能使用这种语法，Python标准库中的`contextlib`模块也提供了对`with`上下文语法的支持，后面再为大家进行讲解。

用`with`上下文语法改写后的代码如下所示。

```Python
try:
    with open('致橡树.txt', 'r', encoding='utf-8') as file:
        print(file.read())
except FileNotFoundError:
    print('无法打开指定的文件!')
except LookupError:
    print('指定了未知的编码!')
except UnicodeDecodeError:
    print('读取文件时解码错误!')
```

### 读写二进制文件

读写二进制文件跟读写文本文件的操作类似，但是需要注意，在使用`open`函数打开文件时，如果要进行读操作，操作模式是`'rb'`，如果要进行写操作，操作模式是`'wb'`。还有一点，读写文本文件时，`read`方法的返回值以及`write`方法的参数是`str`对象（字符串），而读写二进制文件时，`read`方法的返回值以及`write`方法的参数是`bytes-like`对象（字节串）。下面的代码实现了将当前路径下名为`guido.jpg`的图片文件复制到`吉多.jpg`文件中的操作。

```Python
try:
    with open('guido.jpg', 'rb') as file1:
        data = file1.read()
    with open('吉多.jpg', 'wb') as file2:
        file2.write(data)
except FileNotFoundError:
    print('指定的文件无法打开.')
except IOError:
    print('读写文件时出现错误.')
print('程序执行结束.')
```

如果要复制的图片文件很大，一次将文件内容直接读入内存中可能会造成非常大的内存开销，为了减少对内存的占用，可以为`read`方法传入`size`参数来指定每次读取的字节数，通过循环读取和写入的方式来完成上面的操作，代码如下所示。

```Python
try:
    with open('guido.jpg', 'rb') as file1, open('吉多.jpg', 'wb') as file2:
        data = file1.read(512)
        while data:
            file2.write(data)
            data = file1.read()
except FileNotFoundError:
    print('指定的文件无法打开.')
except IOError:
    print('读写文件时出现错误.')
print('程序执行结束.')
```

###  简单的总结

通过读写文件的操作，我们可以实现数据持久化。在Python中可以通过`open`函数来获得文件对象，可以通过文件对象的`read`和`write`方法实现文件读写操作。程序在运行时可能遭遇无法预料的异常状况，可以使用Python的异常机制来处理这些状况。Python的异常机制主要包括`try`、`except`、`else`、`finally`和`raise`这五个核心关键字。**`**try`后面的`except`语句不是必须的，`finally`语句也不是必须的，但是二者必须要有一个**；`except`语句可以有一个或多个，多个`except`会按照书写的顺序依次匹配指定的异常，如果异常已经处理就不会再进入后续的`except`语句；`except`语句中还可以通过元组同时指定多个异常类型进行捕获；`except`语句后面如果不指定异常类型，则默认捕获所有异常；捕获异常后可以使用`raise`要再次抛出，但是不建议捕获并抛出同一个异常；不建议在不清楚逻辑的情况下捕获所有异常，这可能会掩盖程序中严重的问题。最后强调一点，**不要使用异常机制来处理正常业务逻辑或控制程序流程**，简单的说就是不要滥用异常机制，这是初学者常犯的错误。

## 对象的序列化和反序列化

### JSON概述

JSON是“JavaScript Object Notation”的缩写，它本来是JavaScript语言中创建对象的一种字面量语法，现在已经被广泛的应用于跨语言跨平台的数据交换。使用JSON的原因非常简单，因为它结构紧凑而且是纯文本，任何操作系统和编程语言都能处理纯文本，这就是**实现跨语言跨平台数据交换**的前提条件。目前JSON基本上已经取代了XML（可扩展标记语言）作为**异构系统间交换数据的事实标准**。可以在[JSON的官方网站](https://www.json.org/json-zh.html)找到更多关于JSON的知识，这个网站还提供了每种语言处理JSON数据格式可以使用的工具或三方库。

```JavaScript
{
    name: "骆昊",
    age: 40,
    friends: ["王大锤", "白元芳"],
    cars: [
        {"brand": "BMW", "max_speed": 240},
        {"brand": "Benz", "max_speed": 280},
        {"brand": "Audi", "max_speed": 280}
    ]
}
```

上面是JSON的一个简单例子，大家可能已经注意到了，它跟Python中的字典非常类似而且支持嵌套结构，就好比Python字典中的值可以是另一个字典。我们可以尝试把下面的代码输入浏览器的控制台（对于Chrome浏览器，可以通过“更多工具”菜单找到“开发者工具”子菜单，就可以打开浏览器的控制台），浏览器的控制台提供了一个运行JavaScript代码的交互式环境（类似于Python的交互式环境），下面的代码会帮我们创建出一个JavaScript的对象，我们将其赋值给名为`obj`的变量。

```JavaScript
let obj = {
    name: "骆昊",
    age: 40,
    friends: ["王大锤", "白元芳"],
    cars: [
        {"brand": "BMW", "max_speed": 240},
        {"brand": "Benz", "max_speed": 280},
        {"brand": "Audi", "max_speed": 280}
    ]
}
```

<img src="https://github.com/jackfrued/mypic/raw/master/20210820143803.png" alt="image-20210820143756353" width="80%">

上面的`obj`就是JavaScript中的一个对象，我们可以通过`obj.name`或`obj["name"]`两种方式获取到`name`对应的值，如下图所示。可以注意到，`obj["name"]`这种获取数据的方式跟Python字典通过键获取值的索引操作是完全一致的，而Python中也通过名为`json`的模块提供了字典与JSON双向转换的支持。

<img src="https://github.com/jackfrued/mypic/raw/master/20210820144411.png" width="85%">

我们在JSON中使用的数据类型（JavaScript数据类型）和Python中的数据类型也是很容易找到对应关系的，大家可以看看下面的两张表。

表1：JavaScript数据类型（值）对应的Python数据类型（值）

| JSON         | Python       |
| ------------ | ------------ |
| `object`      |`dict`|
| `array`      |`list`|
| `string`     | `str`        |
| `number ` |`int` / `float`|
| `number` (real)   |`float`|
| `boolean` (`true` / `false`) | `bool` (`True` / `False`) |
| `null`       | `None`       |

表2：Python数据类型（值）对应的JavaScript数据类型（值）

| Python                      | JSON                         |
| --------------------------- | ---------------------------- |
| `dict`                      | `object`                     |
| `list` / `tuple`            | `array`                      |
| `str`                       | `string`                     |
| `int` / `float`             | `number`                     |
| `bool` （`True` / `False`） | `boolean` (`true` / `false`) |
| `None`                      | `null`                       |

### 读写JSON格式的数据

在Python中，如果要将字典处理成JSON格式（以字符串形式存在），可以使用`json`模块的`dumps`函数，代码如下所示。

```Python
import json

my_dict = {
    'name': '骆昊',
    'age': 40,
    'friends': ['王大锤', '白元芳'],
    'cars': [
        {'brand': 'BMW', 'max_speed': 240},
        {'brand': 'Audi', 'max_speed': 280},
        {'brand': 'Benz', 'max_speed': 280}
    ]
}
print(json.dumps(my_dict))
```

运行上面的代码，输出如下所示，可以注意到中文字符都是用Unicode编码显示的。

```JSON
{"name": "\u9a86\u660a", "age": 40, "friends": ["\u738b\u5927\u9524", "\u767d\u5143\u82b3"], "cars": [{"brand": "BMW", "max_speed": 240}, {"brand": "Audi", "max_speed": 280}, {"brand": "Benz", "max_speed": 280}]}
```

如果要将字典处理成JSON格式并写入文本文件，只需要将`dumps`函数换成`dump`函数并传入文件对象即可，代码如下所示。

```Python
import json

my_dict = {
    'name': '骆昊',
    'age': 40,
    'friends': ['王大锤', '白元芳'],
    'cars': [
        {'brand': 'BMW', 'max_speed': 240},
        {'brand': 'Audi', 'max_speed': 280},
        {'brand': 'Benz', 'max_speed': 280}
    ]
}
with open('data.json', 'w') as file:
    json.dump(my_dict, file)
```

执行上面的代码，会创建`data.json`文件，文件的内容跟上面代码的输出是一样的。

`json`模块有四个比较重要的函数，分别是：

- `dump` - 将Python对象按照JSON格式序列化到文件中
- `dumps` - 将Python对象处理成JSON格式的字符串
- `load` - 将文件中的JSON数据反序列化成对象
- `loads` - 将字符串的内容反序列化成Python对象

这里出现了两个概念，一个叫序列化，一个叫反序列化，[维基百科](https://zh.wikipedia.org/)上的解释是：“序列化（serialization）在计算机科学的数据处理中，是指将数据结构或对象状态转换为可以存储或传输的形式，这样在需要的时候能够恢复到原先的状态，而且通过序列化的数据重新获取字节时，可以利用这些字节来产生原始对象的副本（拷贝）。与这个过程相反的动作，即从一系列字节中提取数据结构的操作，就是反序列化（deserialization）”。

我们可以通过下面的代码，读取上面创建的`data.json`文件，将JSON格式的数据还原成Python中的字典。

```Python
import json

with open('data.json', 'r') as file:
    my_dict = json.load(file)
    print(type(my_dict))
    print(my_dict)
```

### 包管理工具pip的使用

Python标准库中的`json`模块在数据序列化和反序列化时性能并不是非常理想，为了解决这个问题，可以使用三方库`ujson`来替换`json`。所谓三方库，是指非公司内部开发和使用的，也不是来自于官方标准库的Python模块，这些模块通常由其他公司、组织或个人开发，所以被称为三方库。虽然Python语言的标准库虽然已经提供了诸多模块来方便我们的开发，但是对于一个强大的语言来说，它的生态圈一定也是非常繁荣的。

之前安装Python解释器时，默认情况下已经勾选了安装pip，大家可以在命令提示符或终端中通过`pip --version`来确定是否已经拥有了pip。pip是Python的包管理工具，通过pip可以查找、安装、卸载、更新Python的三方库或工具，macOS和Linux系统应该使用pip3。例如要安装替代`json`模块的`ujson`，可以使用下面的命令。

```Bash
pip install ujson
```

在默认情况下，pip会访问`https://pypi.org/simple/`来获得三方库相关的数据，但是国内访问这个网站的速度并不是十分理想，因此国内用户可以使用豆瓣网提供的镜像来替代这个默认的下载源，操作如下所示。

```Bash
pip install ujson
```

可以通过`pip search`命令根据名字查找需要的三方库，可以通过`pip list`命令来查看已经安装过的三方库。如果想更新某个三方库，可以使用`pip install -U`或`pip install --upgrade`；如果要删除某个三方库，可以使用`pip uninstall`命令。

搜索`ujson`三方库。

```Bash
pip search ujson

micropython-cpython-ujson (0.2)  - MicroPython module ujson ported to CPython
pycopy-cpython-ujson (0.2)       - Pycopy module ujson ported to CPython
ujson (3.0.0)                    - Ultra fast JSON encoder and decoder for Python
ujson-bedframe (1.33.0)          - Ultra fast JSON encoder and decoder for Python
ujson-segfault (2.1.57)          - Ultra fast JSON encoder and decoder for Python. Continuing 
                                   development.
ujson-ia (2.1.1)                 - Ultra fast JSON encoder and decoder for Python (Internet 
                                   Archive fork)
ujson-x (1.37)                   - Ultra fast JSON encoder and decoder for Python
ujson-x-legacy (1.35.1)          - Ultra fast JSON encoder and decoder for Python
drf_ujson (1.2)                  - Django Rest Framework UJSON Renderer
drf-ujson2 (1.6.1)               - Django Rest Framework UJSON Renderer
ujsonDB (0.1.0)                  - A lightweight and simple database using ujson.
fast-json (0.3.2)                - Combines best parts of json and ujson for fast serialization
decimal-monkeypatch (0.4.3)      - Python 2 performance patches: decimal to cdecimal, json to 
                                   ujson for psycopg2
```

查看已经安装的三方库。

```Bash
pip list

Package                       Version
----------------------------- ----------
aiohttp                       3.5.4
alipay                        0.7.4
altgraph                      0.16.1
amqp                          2.4.2
...							  ...
```

更新`ujson`三方库。

```Bash
pip install -U ujson
```

删除`ujson`三方库。

```Bash
pip uninstall -y ujson
```

> **提示**：如果要更新`pip`自身，对于macOS系统来说，可以使用命令`pip install -U pip`。在Windows系统上，可以将命令替换为`python -m pip install -U --user pip`。

### 使用网络API获取数据

如果想在我们自己的程序中显示天气、路况、航班等信息，这些信息我们自己没有能力提供，所以必须使用网络数据服务。目前绝大多数的网络数据服务（或称之为网络API）都是基于[HTTP](https://zh.wikipedia.org/wiki/%E8%B6%85%E6%96%87%E6%9C%AC%E4%BC%A0%E8%BE%93%E5%8D%8F%E8%AE%AE)或HTTPS提供JSON格式的数据，我们可以通过Python程序发送HTTP请求给指定的URL（统一资源定位符），这个URL就是所谓的网络API，如果请求成功，它会返回HTTP响应，而HTTP响应的消息体中就有我们需要的JSON格式的数据。关于HTTP的相关知识，可以看看阮一峰的[《HTTP协议入门》](http://www.ruanyifeng.com/blog/2016/08/http.html)一文。

国内有很多提供网络API接口的网站，例如[聚合数据](https://www.juhe.cn/)、[阿凡达数据](http://www.avatardata.cn/)等，这些网站上有免费的和付费的数据接口，国外的[{API}Search](http://apis.io/)网站也提供了类似的功能，有兴趣的可以自行研究。、[天行数据](https://www.tianapi.com/)、。




[jackfrued/Python-Core-50-Courses: Python语言基础50课 (github.com)](https://github.com/jackfrued/Python-Core-50-Courses)
[Python-Core-50-Courses/第17课：面向对象编程入门.md at master · jackfrued/Python-Core-50-Courses (github.com)](https://github.com/jackfrued/Python-Core-50-Courses/blob/master/%E7%AC%AC17%E8%AF%BE%EF%BC%9A%E9%9D%A2%E5%90%91%E5%AF%B9%E8%B1%A1%E7%BC%96%E7%A8%8B%E5%85%A5%E9%97%A8.md)





