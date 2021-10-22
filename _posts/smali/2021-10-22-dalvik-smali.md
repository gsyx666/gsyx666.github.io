---
layout:     post
title:      "Smali"
subtitle:   "what-is-smali"
date:       2021-10-22 14:43:01
author:     "gsyx"
catalog: true
header-style: text 
tags:
  - Android 逆向
  - Smali
  - Dalvik
---


# dalvik

## 寄存器

在 [Dalvik 字节码][Dalvik 字节码]中，寄存器总是 32 位，可以保存任何类型的值。2 个寄存器（两个相邻的32位寄存器）用于保存 64 位类型（Long 和 Double）。

## dalvik 类型，字段，方法的表示方法

### 类型

 dalvik 只有两种类型，基本类型和引用类型。dalvik 使用这两种类型表示 Java 的全部类型。Java 的对象与数组属于引用类型，其他的 Java 类型都是基本类型。

基本类型共有9个，它们在 dalvik 中的对应关系是：

| Smali            | Java     | 备注                                                         |
| ---------------- | -------- | ------------------------------------------------------------ |
| v                | void     | 只能用于返回值类型                                           |
| Z                | boolean  |                                                              |
| B                | byte     |                                                              |
| S                | short    |                                                              |
| C                | char     |                                                              |
| I                | int      |                                                              |
| J                | long (64 bits)     |                                                              |
| F                | float    |        |                                      
| D                | double (64 bits)   |                    |                                          

引用类型：

* 类在 Smali 中都是用 `L包名路径/类名;` 表示，例如 Android 中的 TextView 类，它的包名是`android.widget`，如果你要在 Smali 中表示这个类，就要写成 `Landroid/widget/TextView;`，最后的分号表示对象名的结束。

* Smali 中通过在类型前面加 [ 来表示该类型的数组，例如 `[I` 表示 int[]，`[Ljava/lang/String;` 表示 String[]，如果要表示多维数组，只需要增加 `[` 的数量，例如 `[[I` 表示二维数组 int[][]

### 方法
> [TypesMethodsAndFields · JesusFreke/smali Wiki (github.com)](https://github.com/JesusFreke/smali/wiki/TypesMethodsAndFields#methods)

dalvik 使用类名、方法名、参数类型和返回类型

```dalvik
Lpackage/name/ObjectName;->MethodName(III)Z
```

在此示例中，`Lpackage/name/ObjectName;` 应该理解为**类型**。 MethodName 是方法的名称。(III)Z 是方法的签名，括号里的 III 方法是参数（这里是三个整形参数），Z (boolen) 是方法返回类型。

**当要表达多个参数类型时，只需简单地将它们连接到一起，例如  (int, int, String)  表示为  (IILjava/lang/String;)**

下面是一个更复杂的示例：

```dalvik
method(I[[IILjava/lang/String;[Ljava/lang/Object;)Ljava/lang/String;
```

在 java 中， 这将是

```java
String method(int, int[][], int, String, Object[])
```

方法格式：
```smali
.method 描述符 方法名(参数类型)返回类型
    方法代码...
.end method
```

### 字段

字段与方法很相似，只是字段没有方法签名域中的参数和返回值，取而代之的是字段的类型。字段格式：
```smali
Lpackage/name/ObjectName;->FieldName:Ljava/lang/String;
```
字段由对类型、字段名（FieldName）、与字段类型（Ljava/lang/String;）组成。其中字段名与字段类型用 `:` 隔开

Smali 中申明字段的语法是：
```smali
.field 描述符 字段名:字段类型
```
例如 Java 代码中定义了 text 字段：
```java
public String text;
```
其对应的Smali代码是：
```smali
.field public text:Ljava/lang/String;
```
当一个字段是 static 和 final （即静态常量）且它的类型是**基本类型**时，可以直接为它赋值：
```smali
.field public static final ID:I = 0x7f0a0001
```
如果定义的字段包含注解，那么语法是：
```smali
.field XXXXX

{注解列表}

.end field
```

## Dalvik指令集
> [Davilk指令集大全](http://pallergabor.uw.hu/androidblog/dalvik_opcodes.html)
### 指令特点

* 根路字节码的大小类型不同，一些字节码添加了后缀来消除歧义。
  * 32 位常规类型字节码未添加任何后缀。
  * 64 位常规类型字节码添加 -wide 后缀。
  * 特殊类型的字节码根据具体的类型添加后缀。它们可以是 -boolean、-byte、-char、-short、-int、-long、-float、-double、-object、-string、-class、-void 之一。
* 根据字节码的布局与选项不同，一些字节码添加了字节码后缀以用来消除歧义。这些后缀通过在字节码主名称后添加“/”来分割开。


> 节选自 [非虫 《Android软件安全与逆向分析》][非虫 《Android软件安全与逆向分析》]

### 空指令

空指令的助记符为 nop。它的值位 00，通常 nop 指令用来作对齐代码之用，无实际操作。

### 数据操作指令

### 返回指令

### 数据定义指令

### 锁指令

### 实例操作指令

### 数组操作指令

### 异常指令

### 跳转指令

### 比较指令

### 字段操作指令

### 方法调用指令

### 数据转换指令

### 数据运算指令


# smali

> Smali 实质上就是 Java 字节码，一句 Java 代码会对应多句 Smali 代码（如果你不知道什么是字节码，那汇编总听过吧，两者有点类似，要是汇编也没听过，emmmm。。自个百度去）。

## 详解smali文件

上面我们介绍了Dalvik的相关指令,下面我们则来认识一下smali文件.尽管我们使用java来写Android应用,但是Dalvik并不直接加载.class文件,而是通过dx工具将.class文件优化成.dex文件,然后交由Dalvik加载.这样说来,我们无法通过分析.class来直接分析apk文件,而是需要借助工具baksmali.jar反编译dex文件来获得对应smali文件,smali文件可以认为是Davilk的字节码文件,但是并两者并不完全等同.

通过baksmali.jar反编译出来每个.smali,都对应与java中的一个类,每个smali文件都是Davilk指令组成的,并遵循一定的结构.smali存在很多的指令用于描述对应的java文件,所有的指令都以”.”开头,常用的指令如下:

| 关键词 |	说明 |
| ---- | ---- | 
| .filed	| 定义字段|
.method…end method	定义方法
.annotation…end annotation	定义注解
.implements	定义接口指令
.local	指定了方法内局部变量的个数
.registers	指定方法内使用寄存器的总数
.prologue	表示方法中代码的开始处
.line	表示java源文件中指定行
.paramter	指定了方法的参数
.param	和.paramter含义一致,但是表达格式不同

在这里很多人对.local和.register感到困惑,如果你也是请重新看上面的有关寄存器的点。


--------



smali 和 baksmali 则是针对 DEX 执行文件格式的汇编器和反汇编器，反汇编后 DEX 文件会产生.smali 后缀的代码文件，smali 代码拥有特定的格式与语法，smali 语言是对 Dalvik 虚拟机字节码的一种解释。目前ART虚拟机相较于dalvik虚拟机算是一种升级，没有本质的区别。 - 来自[Android逆向之Smali汇编](https://zhuanlan.zhihu.com/p/266603183#:~:text=smali%20和%20baksmali%20则是针对%20DEX%20执行文件格式的汇编器和反汇编器，反汇编后,DEX%20文件会产生.smali%20后缀的代码文件，smali%20代码拥有特定的格式与语法，smali%20语言是对%20Dalvik%20虚拟机字节码的一种解释。)
## 数据类型 Type

> [TypesMethodsAndFields · JesusFreke/smali Wiki (github.com)](https://github.com/JesusFreke/smali/wiki/TypesMethodsAndFields#types)

在Java中类型分为基本类型和引用类型

基本类型共有9个，它们在Smali中的对应关系是：

| Smali            | Java     | 备注                                                         |
| ---------------- | -------- | ------------------------------------------------------------ |
| v                | void     | 只能用于返回值类型                                           |
| Z                | boolean  |                                                              |
| B                | byte     |                                                              |
| S                | short    |                                                              |
| C                | char     |                                                              |
| I                | int      |                                                              |
| J                | long     |                                                              |
| F                | float    |                                                              |
| D                | double   |                                                              |
|                  |          | 以上是基本类型                                               |
| `Lpackage/name;` | 对象类型 | `L`表示这是一个对象类型，`package/name`表示该对象所在的包，`；`表示对象名称的结束<br/> `Lpackage/name/ObjectName;` 相当于`java`中的`package.name.ObjectName;` |
| `[类型`          | 数组     | `[I`表示一个`int`型`数组，`[Ljava/lang/String`表示一个`String`的对象`数组` 如果要表示多维数组，只需要增加[的数量，例如[[I表示二维数组int[][] |

## 方法 - Methods



### 表示方法




### 方法定义格式



其中参数类型可以有0个或多个，返回类型必须是一个。

###  调用方法

Smali中必须以非常详细的形式指定要调用的方法，包括类名、方法名、参数类型和返回类型，其具体形式是：类名->方法名(参数类型)返回类型

例如：

```smali
System.out.println("Hello world");
```

其中 out 是 System 的一个静态字段，它的类型是 PrintStream，println 是 PrintStream 中的一个方法

所以在上一篇的例子中，最后调用 println 方法是通过：

```smali
invoke-virtual {v0, v1}, Ljava/io/PrintStream;->println(Ljava/lang/String;)V
```


后面那部分正是方法 println 的完整表达形式

### 方法类型

* `direct method`= private方法
* `virtual method` = 其余的方法

* 方法调用
  * 格式
```java
invoke-指令类型 {参数1, 参数2,...}, L类名;->方法名
```
  * 包含
    * invoke-direct
    * invoke-virtual
    * invoke-static
    * invoke-super
    * invoke-interface
* 函数返回结果
  * 要用指令move-result或move-result-object来保存函数返回的结果
  
  
 


----

References

* [深入理解Dalvik字节码指令及Smali文件][深入理解Dalvik字节码指令及Smali文件]
* [Home · JesusFreke/smali Wiki (github.com)](https://github.com/JesusFreke/smali/wiki)
* [ruanyf/document-style-guide: 中文技术文档的写作规范 (github.com)](https://github.com/ruanyf/document-style-guide)
* [非虫 《Android软件安全与逆向分析》][非虫 《Android软件安全与逆向分析》]

[非虫 《Android软件安全与逆向分析》]: https://douban.com/book/subject/20556210/

[深入理解Dalvik字节码指令及Smali文件]: https://blog.csdn.net/dd864140130/article/details/52076515

[Dalvik 字节码]:[https://source.android.google.cn/devices/tech/dalvik/dalvik-bytecode.html]

本文部分图片来自 网络
