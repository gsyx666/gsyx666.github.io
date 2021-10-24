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


# smali

## 介绍

在执行 Android Java 层的代码时，其实就是 Dalvik （ART） 虚拟机（使用 C或 C++ 代码实现）在解析 Dalvik 字节码，从而模拟程序的执行过程。

二进制 Dalvik 字节这平台实际理解的格式。但是，读取或修改二进制代码并不容易，因此有一些工具可以在人类可读的表示形式之间进行转换。最常见的人类可读格式称为 Smali。这与您提到的反汇编程序基本相同。

例如，假设您有执行类似操作的 Java 代码
```java
int x = 42
```
假设这是第一个变量，那么该方法的 dex 代码很可能包含十六进制序列
```
13 00 2A 00
```
如果你在它上面运行 baksmali，你会得到一个包含该行的文本文件
```smali
const/16 v0, 42
```
**这显然比二进制代码更具可读性。但是平台对smali一无所知，它只是一个使字节码更容易工作的工具。**

Dalvik 和 ART 都采用包含 dalvik 字节码的 .dex 文件。它对应用程序开发人员是完全透明的，唯一的区别是安装和运行应用程序时幕后发生的事情。

## 寄存器

在 [Dalvik 字节码][Dalvik 字节码]中，寄存器总是 32 位，可以保存任何类型的值。2 个寄存器（两个相邻的32位寄存器）用于保存 64 位类型（Long 和 Double）。
那么什么是寄存器呢？你可以把它认为是变量，或者是暂时存放东西的地方。

举个例子：

有一个静态方法 `abc(String)`，如果你要在Java方法中调用这个方法，直接输入 `abc("Hello");`就行了。

而在 Smali 中，你不能直接把字符串参数传递给方法，你需要一个寄存器（比如 v0），先把"Hello"放到 v0 中，然后再调用 `abc` 方法，并告诉它你需要的参数在v0 里面，自己去拿吧。
```smali
# 定义一个字符串常量"Hello"放到v0中
const-string v0, "Hello"
# 调用abc方法，需要的参数放在v0中
invoke-static {v0}, LXX;->abc(Ljava/lang/String;)V
```
现在大家理解什么是寄存器了吧。

### 寄存器声明

在执行具体方法时，Dalvik 会根据  `.registers`  指令来确定该函数要用到的寄存器数目，虚拟机会根据申请的寄存器的数目来为该方法分配相应大小的栈空间，dalvik 在对这些寄存器操作时，其实都是在操作栈空间。

**需要在方法的开头用`.registers N`来指定寄存器的数量，然后才可以使用寄存器 v0 到 v(N-1)。**

### 寄存器命名规则

一个方法所申请的寄存器会分配给函数方法的参数 (parameter) 以及局部变量 (local variable) 。在 smali 中，一般有两种命名规则

- v 命名法 （本文不介绍）
- p 命名法


### 参数寄存器

上面说的都是普通寄存器 vN，另外 Smali 还特意定义了一种参数寄存器 pN ，用于存放这个方法传入的参数的值。

**如果一个方法有 n 个寄存器，有 m 个参数，那么 n 必须大于等于 m，并且 n 个寄存器的后面 m 个是参数寄存器，举个例子：**

某个静态方法 abc(int, int, int)，**它一共有 3 个参数**，如果它一共有 5 个寄存器（通过`.registers N`定义，**N 不能小于 3**），就是 `.registers 5`

|普通寄存器|对应参数寄存器|
|---|---|
|v0| |	
|v1| |	
|v2|p0|
|v3|p1|
|v4|p2|

当我调用 abc(11, 22, 33) 时，p0 中的值初始化为 11，p1 中的值初始化为 22，p2 中的值初始化为 33，v0 和v1 不会初始化。

|普通寄存器|参数寄存器|初始化|
|---|---|---|
|v0| | |
|v1| | |
|v2|p0|11|
|v3|p1|22|
|v4|p2|33|

当我把寄存器数量改成 6（.registers 6），寄存器就会变成下表所示：

|普通寄存器|参数寄存器|初始化|
|---|---|---|
|v0| | |
v1| | |
v2| | |		
|v3|p0|11|
|v4|p1|22|
|v5|p2|33|

思考一下，如果不使用参数寄存器，代码中全部用vN，那么改变寄存器数量后，你还得改多少代码？

### 隐藏的参数

对于非静态方法，它的参数寄存器数量比实际参数多了一个，p0 会固定用于表示当前类实例（Java 中的 this），从 p1 开始才是真正的参数，我们可以通过Java2Smali 工具来验证一下。
Java 代码如下：

![](/img/in-post/smali/1.png)

test1() 和 test2() 的唯一区别就是一个是静态一个非静态

test1() 的Smali代码：

![test1-smali.png](/img/in-post/smali/test1-smali.png)

test2()的Smali代码：

![test2-smali.png](/img/in-post/smali/test2-smali.png)

两个方法都是依次打印出两个参数，test1()中24行是打印第一个参数用的是p0，29行是打印第二个参数用的是p1；对照下test2()中则分别用的是p1和p2。

那test2()中的p0真的代表this吗？我们也可以修改代码验证下：

![test2-java.png](/img/in-post/smali/test2-java.png)

![test2-java2.png](/img/in-post/smali/test2-java2.png)


## smali 类型，字段，方法的表示方法

### 类型

 dalvik 只有两种类型，基本类型和引用类型。dalvik 使用这两种类型表示 Java 的全部类型。Java 的对象与数组属于引用类型，其他的 Java 类型都是基本类型。

基本类型共有9个，它们在 smali 中的对应关系是：

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

Smali 使用类名、方法名、参数类型和返回类型

```smali
Lpackage/name/ObjectName;->MethodName(III)Z
```

在此示例中，`Lpackage/name/ObjectName;` 应该理解为**类型**。 MethodName 是方法的名称。(III)Z 是方法的签名，括号里的 III 方法是参数（这里是三个整形参数），Z (boolen) 是方法返回类型。

**当要表达多个参数类型时，只需简单地将它们连接到一起，例如  (int, int, String)  表示为  (IILjava/lang/String;)**

下面是一个更复杂的示例：

```smali
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
字段由对类型、字段名（FieldName）和字段类型（Ljava/lang/String;）组成。其中字段名与字段类型用 `:` 隔开

**Smali 中声明字段的语法是：**

```smali
#instance fields
.field <访问权限修饰符> [非权限修饰符] <字段名>:<字段类型>
```
其中访问权限修饰符可以为

- public
- private
- protected

非权限修饰符可以为（**查明其用法!!!**）

- final
- volidate
- transient

例如 Java 代码中定义了 text 字段：
```java
public java.lang.String text;
```
其对应的Smali代码是：
```smali
# instance fields
.field public text:Ljava/lang/String;
```

**静态字段**

```smali
#static fields
.field <访问权限> static [修饰词] <字段名>:<字段类型>
```
当一个字段是 static 和 final （即**静态常量**）且它的类型是**基本类型**时，可以直接为它赋值：
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

### Dalvik 指令格式 

在介绍 smali 语法中的指令之前，我们先来看看 Dalvik 指令的基本格式。

Dalvik 中指令的格式主要包含两个方面：位描述，格式 ID。目前 Dalvik 中基本上所有的指令如下图所示，其中第一列给出了指令按照位进行描述的格式，第二列是格式化 ID ，第三列表示相应的句法，第四列对其进行说明

![](/img/in-post/smali/Dalvik-Executable-instruction-formats.png)

**位描述**

在位描述中，Davik 中的每一类指令一般由如下的元素构成

* 一个 op，8 位指令码
* 若干个字符，每一个字符表示 4 位
* 若干个 | ，进行分割，方便阅读。
* 若干个 
∅
 ，同样也是 4 个字符，表示该部分位为 0。
 
此外，在上面的展现形式种，指令由一个或者多个空格分割的 16 位的 word 组成，其中每一个 word 可以包含上述的几个元素。

举个例子，指令 B|A|op CCCC 包含 2 个 word，一共 32 位。其中，第一个字的低 8 位是操作码，中间 4 位是 A，高 4 位是 B。第二个字是单独的 16 位的数值。

**格式 ID**

但是，正如表格里所展现的

![](/img/in-post/smali/Dalvik-Instruction-sample.png)
这样的一种指令格式，根据ID的不同，仍然可以表示不同的指令含义。

一般来说，格式ID由若干个字符组成，一般来说包含3个字符

- 第一个数字表示word的数量

- 第二个

    - 数字的话，表示指令包含的寄存器的最大数量（这是因为有些指令可以包含不定个数的寄存器）
    - r的话，表示使用了一定范围内的寄存器(range)。

- 第三个字符表示指令使用到的额外数据的类型。如下表

  | Mnemonic | Bit Sizes | Meaning                                  |
  | -------- | --------- | ---------------------------------------- |
  | b        | 8         | immediate signed byte                    |
  | c        | 16, 32    | constant pool index                      |
  | f        | 16        | interface constants (only used in statically linked formats) |
  | h        | 16        | immediate signed hat (high-order bits of a 32- or 64-bit value; low-order bits are all `0`) |
  | i        | 32        | immediate signed int, or 32-bit float    |
  | l        | 64        | immediate signed long, or 64-bit double  |
  | m        | 16        | method constants (only used in statically linked formats) |
  | n        | 4         | immediate signed nibble                  |
  | s        | 16        | immediate signed short                   |
  | t        | 8, 16, 32 | branch target                            |
  | x        | 0         | no additional data                       |

- 如果存在第四个字符的话

  - s表示采用静态链接
  - i表示指令应该被内联处理。
  
 **句法**
 
 其基本要求如下

- 指令以操作码op开始，后面直接跟上一个或者多个参数，参数间以逗号分隔。
- 指令的参数从指令第一部分开始，op位于低8位，高8位可以是一个8位的参数，也可以是两个4位的参数，还可以为空。如果指令超过16位，则后面部分依次作为参数。
- 参数`Vx`表示寄存器，如v0、v1等。这里之所以采用v而不用r是为了避免与实现该虚拟机架构的机器架构中的寄存器命名产生冲突。
- 参数 `#+X` 表示常量数字。
- 参数 `+X` 表示相对指令的地址偏移。
- 参数 `kind@X`  表示常量池索引值，其中kind表示常量池类型，可以是以下四种类型
    - string，字符串常量池索引
    - type，类型常量池索引
    - field，字段常量池索引
    - meth，方法常量池索引

以指令 `op vAA, type@BBBB` 为例，指令使用了1个寄存器vAA，一个32位的类型常量池索引。
 
### 指令特点

Dalvik指令在调用规范上大致模仿常见的架构和 C 样式的调用规范，如下

- 参数顺序为 Dest-then-source 。

- 利用后缀用来表明运算类型，从而消除歧义：

    - 32 位常规类型字节码未添加任何后缀。
    - 64 位常规类型字节码添加 -wide 后缀。
    - 特殊类型的字节码根据具体的类型添加后缀。它们可以是 -boolean、-byte、-char、-short、-int、-long、-float、-double、-object、-string、-class、-void 之一。

- 根据字节码的布局与选项不同，一些字节码添加了字节码后缀以用来消除歧义。这些后缀通过在字节码主名称后添加“/”来分割开。


  例如，在指令`move-wide/from16 vAA, vBBBB` 中

  - `move`为基础运算码，表示这是基本运算，用来移动寄存器的值。
  - `wide`为名称后缀，表示指令对64 位数据进行运算。
  - `from16`为运算码后缀，表示源为一个 16 位寄存器的引用变量。
  - `vAA`为目的寄存器，取值范围为 `v0` - `v255`。
  - `vBBBB`为源寄存器，取值范围为 `v0` - `v65535`。


> 节选自 [非虫 《Android软件安全与逆向分析》][非虫 《Android软件安全与逆向分析》]

### 空指令

空指令的助记符为 nop。它的值位 00，通常 nop 指令用来作对齐代码之用，无实际操作。

### 数据操作指令

数据操作指定为 move。move 的指定操作原型为move destination。move 指令根据字节码的大小与类型不同，后面会跟上不同的后缀。

| op&id  | 语法                            | 参数                                  | 说明                              |
| ------ | ----------------------------- | :---------------------------------- | ------------------------------- |
| 01 12x | move vA, vB                   | `A:` 目标寄存器（4 位）`B:` 源寄存器（4 位）       | vA=vB                           |
| 02 22x | move/from16 vAA, vBBBB        | `A:` 目标寄存器（8 位）`B:` 源寄存器（16 位）      | vAA=vBBBB                       |
| 03 32x | move/16 vAAAA, vBBBB          | `A:` 目标寄存器（16 位）`B:` 源寄存器（16 位）     | vAAAA=VBBBB                     |
| 04 12x | move-wide vA, vB              | `A:` 目标寄存器对（4 位）`B:` 源寄存器对（4 位）     | vA，v(A+1)=vB，V(B+1)             |
| 05 22x | move-wide/from16 vAA, vBBBB   | `A:` 目标寄存器对（8 位）`B:` 源寄存器对(16 bit)  | vAA，v(AA+1)=vBBBB，V(BBBB+1)     |
| 06 32x | move-wide/16 vAAAA, vBBBB     | `A:` 目标寄存器对（16 位）`B:` 源寄存器对(16 bit) | vAAAA，v(AAAA+1)=vBBBB，V(BBBB+1) |
| 07 12x | move-object vA, vB            | `A:` 目标寄存器（4 位）`B:` 源寄存器（4 位）       | 对象引用赋值，vA=vB                    |
| 08 22x | move-object/from16 vAA, vBBBB | `A:` 目标寄存器（8 位）`B:` 源寄存器（16 位）      | 对象引用赋值，vAA=vBBBB                |
| 09 32x | move-object/16 vAAAA, vBBBB   | `A:` 目标寄存器（16 位）`B:` 源寄存器（16 位）     | 对象引用赋值，vAAAA=vBBBB              |
| 0a 11x | move-result vAA               | `A:` 目标寄存器（8 位）                     | 将函数调用返回值放到VAA寄存器中。              |
| 0b 11x | move-result-wide vAA          | `A:` 目标寄存器对（8 位）                    | 将函数调用返回值放到VAA寄存器中。              |
| 0c 11x | move-result-object vAA        | `A:` 目标寄存器（8 位）                     | 将函数调用返回对象引用VAA寄存器中。             |
| 0d 11x | move-exception vAA            | `A:` 目标寄存器（8 位）                     | 将捕获的异常保存到给定寄存器中。                |

其中，`move`系列指令以及`move-result` 用于处理小于等于 32 位的基本类型。

`move-wide`系列指令和`move-result-wide`用于处理64位类型，包括`long`和`double`类型。

`move-object`系列指令和`move-result-object`用于处理对象引用。

此外，后缀（`/from16`、`/16`）只影响字节码的位数和寄存器的范围，不影响指令的逻辑。


### 返回指令

在 Java 中我们会利用 return 返回方法的执行结果。同样的，在 Davilk 中我们也需要 return 指令来返回方法运行结果。

| 指令                | 说明             |
| ----------------- | -------------- |
| return-void       | 什么也不返回         |
| return vAA        | 返回一个32位非对象类型的值 |
| return-wide vAA   | 返回一个64位非对象类型的值 |
| return-object vAA | 返回一个对象类型的引用    |

### 数据定义指令

数据定义用来定义程序中用到的常量、字符串和类等数据。它的基础字节码为 const。

| op&id  | 语法                                       | 参数                                       | 说明                                       |
| ------ | ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| 2 11n  | const/4 vA, #+B                          | `A:` 目标寄存器（4 位）           `B:` 有符号整数（4 位） | 将给定的值（符号扩展为 32 位）移到指定的寄存器中。              |
| 13 21s | const/16 vAA, #+BBBB                     | `A:` 目标寄存器（8 位）           `B:` 有符号整数（16 位） | 将给定的值（符号扩展为 32 位）移到指定的寄存器中。              |
| 14 31i | const vAA, #+BBBBBBBB                    | `A:` 目标寄存器（8 位）           `B:` 任意 32 位常量 | 将给定的值移到指定的寄存器中。                          |
| 15 21h | const/high16 vAA, #+BBBB0000             | `A:` 目标寄存器（8 位）           `B:` 有符号整数（16 位） | 将给定的值（右零扩展为 32 位）移到指定的寄存器中。              |
| 16 21s | const-wide/16 vAA, #+BBBB                | `A:` 目标寄存器（8 位）           `B:` 有符号整数（16 位） | 将给定的值（符号扩展为 64 位）移到指定的寄存器对中。             |
| 17 31i | const-wide/32 vAA, #+BBBBBBBB            | `A:` 目标寄存器（8 位）            `B:` 有符号整数（32 位） | 将给定的值（符号扩展为 64 位）移到指定的寄存器对中。             |
| 18 51l | const-wide vAA, #+BBBBBBBBBBBBBBBB       | `A:` 目标寄存器（8 位）           `B:` 任意双字宽度（64 位）常量 | 将给定的值移到指定的寄存器对中。                         |
| 19 21h | const-wide/high16 vAA, #+BBBB000000000000 | `A:` 目标寄存器（8 位）           `B:` 有符号整数（16 位） | 将给定的值（右零扩展为 64 位）移到指定的寄存器对中。             |
| 1a 21c | const-string vAA, string@BBBB            | `A:` 目标寄存器（8 位）           `B:` 字符串索引     | 将给定的字符串引用赋值给指定的寄存器中。                     |
| 1b 31c | const-string/jumbo vAA, string@BBBBBBBB  | `A:` 目标寄存器（8 位）            `B:` 字符串索引    | 将给定字符串引用（较大）赋值到指定的寄存器中。                  |
| 1c 21c | const-class vAA, type@BBBB               | `A:` 目标寄存器（8 位）           `B:` 类型索引      | 将给定类引用赋值到指定的寄存器中。如果指定的类型是原始类型，则将存储对原始类型的退化类的引用。 |

举个例子，如果java代码如下

```java
boolean z = true;
z = false;
byte b = 1;
short s = 2;
int i = 3;
long l = 4;
float f = 0.1f;
double d = 0.2;
String str = "test";
Class c = Object.class;
```

那么编译之后得到的代码如下

```smali
const/4 v10, 0x1
const/4 v10, 0x0
const/4 v0, 0x1
const/4 v8, 0x2
const/4 v5, 0x3
const-wide/16 v6, 0x4
const v4, 0x3dcccccd    # 0.1f
const-wide v2, 0x3fc999999999999aL    # 0.2
const-string v9, "test"
const-class v1, Ljava/lang/Object;
```

可以看出，根据数据类型大小的不同，会采用不同的语法。此外，我们可以看到float的字面值是0x3dcccccd，这其实就是0.1。关于浮点数在计算机中的存在形式，请自行网上搜索。此外，一般来说，smali会自动帮我们将string的id转换为其真正的字符串。

### 锁指令

锁指令用于在多线程程序。包含以下两个指令

| **指令**            | **说明**    |
| ----------------- | --------- |
| monitor-enter vAA | 为指定的对象获取锁 |
| monitor-exit vAA  | 释放指定的对象的锁 |

### 实例操作指令
实例操作指令主要实现了实例的类型转换，检查及新建等功能。

| **指令**                                   | **说明**                                   |
| ---------------------------------------- | ---------------------------------------- |
| check-cast vAA, type@BBBB                | 将vAA寄存器中的对象引用转换成type@BBBB类型，如果失败的话，抛出ClassCastException异常。如果类型B指定的是基本类型，对于非基本类型的A来说，运行时始终会失败 |
| instance-of vA, vB, type@CCCC            | 判断vB寄存器中的对象引用是否可以转换成指定的类型，如果可以，vA寄存器被赋值为1，否则vA寄存器被 赋值为0。 |
| new-instance vAA, type@BBBB              | 构造一个指定类型对象的新实例，并将对象引用赋值给vAA寄存器，类型符type指定的类型不能是数组类 |
| check-cast/jumbo vAAAA, type@BBBBBBBB    | 功能与check-cast vAA, type@BBBB相同，只是寄存器值与指令的索引取值范围更大（Android4.0中新增的指令） |
| instance-of/jumbo vAAAA, vBBBB, type@CCCCCCCC | 功能与instance-of vA, vB, type@CCCC相同，只是寄存器值与指令的索引取值范围更大（Android4.0中新增的指令） |
| new-instance/jumbo vAAAA, type@BBBBBBBB  | 功能与new-instance vAA, type@BBBB相同，只是寄存器值与指令的索引取值范围更大（Android4.0中新增的指令） |

比如，我们定义一个实例

```java
Object obj = new Object();
```

其对应的smali代码如下

```smali
new-instance v0, Ljava/lang/Object;
invoke-direct-empty {v0}, Ljava/lang/Object;-><init>()V
```

再比如我们可以进行如下的类型判断

```java
String s = "test";
boolean b = s instanceof String;
```

其对应的smali代码如下

```smali
const-string v0, "test"
instance-of v1, v0, Ljava/lang/String;
```

如果我们进行类型的强制转换

```java
String s = "test";
Object o = (Object)s;
```

其对应的smali代码如下

```smali
const-string v0, "test"
check-cast v0, Ljava/lang/Object;
move-object v1, v0
```
### 数组操作指令

数组操作指令中实现了获取数组长度，新建数组，数组赋值，数组元素取值与赋值等操作。

| **指令**                                   | **说明**                                   |
| ---------------------------------------- | ---------------------------------------- |
| array-length vA, vB                      | 获取给定vB寄存器中数组的长度并赋给vA寄存器，数组长度指的是数组中的元素个数。 |
| new-array vA, vB, type@CCCC              | 构造大小为vB的元素类型为type@CCCC的数组，并将引用赋给vA寄存器    |
| filled-new-array {vC, vD, vE, vF, vG},type@BBBB | 构造大小vA的元素类型为type@BBBB的数组并填充数组内容。vA寄存器是隐含使用的，除了指定数组的大小外还指定了参数的个数，vC~vG是使用到的参数寄存序列 |
| filled-new-array/range {vCCCC  ..vNNNN}, type@BBBB | 指令功能与filled-new-array {vC, vD, vE, vF, vG},type@BBBB相同，只是参数寄存器使用range后缀指定了取值范围 ，vC是第一个参数寄存器，N = A +C -1 |
| fill-array-data vAA, +BBBBBBBB           | 用指定的数据来填充数组，vAA寄存器为数组引用，引用必须为基础类型的数组，在指令后面会紧跟一个数据表 |
| new-array/jumbo vAAAA, vBBBB,type@CCCCCCCC | 指令功能与new-array vA,vB,type@CCCC相同，但是寄存器值与指令的索引取值范围更大（Android4.0中新增的指令） |
| filled-new-array/jumbo {vCCCC  ..vNNNN},type@BBBBBBBB | 指令功能与filled-new-array/range {vCCCC  ..vNNNN},type@BBBB相同，只是索引取值范围更大（Android4.0中新增的指令） |
| arrayop vAA, vBB, vCC                    | 对vBB寄存器指定的数组元素进行取值与赋值。vCC寄存器指定数组元素索引，vAA寄存器用来存放读取的或需要设置的数组元素的值。读取元素使用aget类指令，元素赋值使用aput类指定，根据数组中存储的类型指令后面会紧跟不同的指令后缀，指令列表如下：aget, aget-wide, aget-object, aget-boolean, aget-byte,aget-char, aget-short, aput, aput-wide, aput-object, aput-boolean, aput-byte, aput-char, aput-short。 |

我们可以定义数组如下

```java
int[] arr = new int[10];
```

其对应的smali如下

```smali
const/4 v1, 0xa
new-array v0, v1, I
```

如果我们直接在定义时，对数组进行初始化，如下

```smali
int[] arr = {1, 2, 3, 4, 5};
```

对应的smali如下

```smali
const/4 v1, 0x1
const/4 v2, 0x2
const/4 v3, 0x3
const/4 v4, 0x4
const/4 v5, 0x5
filled-new-array {v1, v2, v3, v4, v5}, I
move-result v0
```

在寄存器连续的情况下，还可以写成如下代码

```smali
const/4 v1, 0x1
const/4 v2, 0x2
const/4 v3, 0x3
const/4 v4, 0x4
const/4 v5, 0x5
filled-new-array-range {v1..v5}, I
move-result v0
```
### 异常指令
用来抛出异常

利用 throw vAA 指令抛出vAA寄存器中指定类型的异常。

##### try catch

首先，我们来看一下try catch，如下

```java
int a = 10;
try {
    callSomeMethod();
} catch (Exception e) {
    a = 0;
}
callAnotherMethod();
```

对应的smali如下

```smali
const/16 v0, 0xa

:try_start_0            # try 块开始
invoke-direct {p0}, Lnet/flygon/myapplication/SubActivity;->callSomeMethod()V
:try_end_0              # try 块结束

.catch Ljava/lang/Exception; {:try_start_0 .. :try_end_0} :catch_0

:goto_0
invoke-direct {p0}, Lnet/flygon/myapplication/SubActivity;->callAnotherMethod()V
return-void

:catch_0                # catch 块开始
move-exception v1
const/4 v0, 0x0
goto :goto_0            # catch 块结束
```

可以看到，`:try_start_0`和`:try_end_0`之间如果存在异常，则会向下寻找`.catch`（或者`.catch-all`）语句，符合条件时跳到标签的位置，这里是`:catch_0`，结束之后会有个`goto`跳回去。

##### try-finally

java代码如下

```java
int a = 10;
try {
    callSomeMethod();
} finally {
    a = 0;
}
callAnotherMethod();
```

其对应的smali代码如下

```smali
const/16 v0, 0xa

:try_start_0            # try 块开始
invoke-direct {p0}, Lnet/flygon/myapplication/SubActivity;->callSomeMethod()V
:try_end_0              # try 块结束

.catchall {:try_start_0 .. :try_end_0} :catchall_0

const/4 v0, 0x0         # 复制一份到外面
invoke-direct {p0}, Lnet/flygon/myapplication/SubActivity;->callAnotherMethod()V
return-void

:catchall_0             # finally 块开始
move-exception v1
const/4 v0, 0x0
throw v1                # finally 块结束
```

可以看出，由于`finally`中的逻辑无论有没有异常都会执行，所以代码里一共有两部分。

##### try-catch-finally

当我们同时使用catch与finally时，如下

```java
int a = 10;
try {
    callSomeMethod();
} catch (Exception e) {
    a = 1;
}
finally {
    a = 0;
}
callAnotherMethod();
```

其对应的smali代码如下

```smali
const/16 v0, 0xa

:try_start_0            # try 块开始
invoke-direct {p0}, Lnet/flygon/myapplication/SubActivity;->callSomeMethod()V
:try_end_0              # try 块结束

.catch Ljava/lang/Exception; {:try_start_0 .. :try_end_0} :catch_0
.catchall {:try_start_0 .. :try_end_0} :catchall_0

const/4 v0, 0x0         # 复制一份到外面

:goto_0
invoke-direct {p0}, Lnet/flygon/myapplication/SubActivity;->callAnotherMethod()V
return-void

:catch_0                # catch 块开始
move-exception v1
const/4 v0, 0x1
const/4 v0, 0x0         # 复制一份到 catch 块里面
goto :goto_0            # catch 块结束

:catchall_0             # finally 块开始
move-exception v2
const/4 v0, 0x0
throw v2                # finally 块结束
```

### 跳转指令

跳转指令实现了从当前地址跳转到指定的偏移处的操作。Dalvik指令集中有三种跳转指令

- goto，无条件跳转
- switch，分支跳转
- if，条件跳转

##### goto指令

如下

| 指令                | 含义                      |
| ----------------- | ----------------------- |
| goto +AA          | 无条件跳转到指定偏移处，偏移量AA不能为0   |
| goto/16 +AAAA     | 无条件跳转到指定偏移处，偏移量AAAA不能为0 |
| goto/32 +AAAAAAAA | 无条件跳转到指定偏移处             |

##### if指令

if指令中主要分为两种if-test与if-testz。`if-test vA,vB,+CCCC` 会比较vA与v，如果比较结果满足就跳转到CCCC指定的偏移处（相对当前偏移），偏移量CCCC不能为0。if-test类型的指令如下：

| 指令                   | 说明           |
| -------------------- | ------------ |
| `if-eq vA,vB,target` | 如果vA=vB，跳转。  |
| `if-ne vA,vB,target` | 如果vA!=vB，跳转。 |
| `if-lt vA,vB,target` | 如果vA<vB，跳转。  |
| `if-gt vA,vB,target` | 如果vA>vB，跳转。  |
| `if-ge vA,vB,target` | 如果vA>=vB，跳转。 |
| `if-le vA,vB,target` | 如果vA<=vB，跳转。 |

if-testz类型的指令如下

| 指令                | 说明          |
| ----------------- | ----------- |
| if-eqz vAA,target | 如果vA=0，跳转。  |
| if-nez vAA,target | 如果vA!=0，跳转。 |
| if-ltz vAA,target | 如果vA<0，跳转。  |
| if-gtz vAA,target | 如果vA>0，跳转。  |
| if-lez vAA,target | 如果vA<=0，跳转。 |
| if-gtz vAA,target | 如果vA>=0，跳转。 |

举个例子，java代码如下

```java
int a = 10
if(a > 0)
    a = 1;
else
    a = 0;
```

smali代码如下

```smali
const/4 v0, 0xa
if-lez v0, :cond_0 # if 块开始
const/4 v0, 0x1
goto :cond_1       # if 块结束
:cond_0            # else 块开始
const/4 v0, 0x0
:cond_1            # else 块结束
```

在只有if的情况下

```java
int a = 10;
if(a > 0)
    a = 1;
```

smali代码如下

```smali
const/4 v0, 0xa
if-lez v0, :cond_0 # if 块开始
const/4 v0, 0x1
:cond_0            # if 块结束
```

##### switch指令

如下

| 指令                          | 含义                                       |
| --------------------------- | ---------------------------------------- |
| packed-switch vAA,+BBBBBBBB | vAA寄存器为switch分支中需要判断的值，BBBBBBBB指向一个packed-switch-payload格式的偏移表，表中的值是有规律递增的。 |
| sparse-switch vAA,+BBBBBBBB | vAA寄存器为switch分支中需要判断的值，BBBBBBBB指向一个sparse-switch-payload格式的偏移表，表中的值是无规律的偏移表，表中的值是无规律的偏移量。 |

对于第一种递增式的switch，如下

```java
int a = 10;
switch (a){
    case 0:
        a = 1;
        break;
    case 1:
        a = 5;
        break;
    case 2:
        a = 10;
        break;
    case 3:
        a = 20;
        break;
}
```

对应的smali如下

```smali
const/16 v0, 0xa

packed-switch v0, :pswitch_data_0 # switch 开始

:pswitch_0                        # case 0
const/4 v0, 0x1
goto :goto_0

:pswitch_1                        # case 1
const/4 v0, 0x5
goto :goto_0

:pswitch_2                        # case 2
const/16 v0, 0xa
goto :goto_0

:pswitch_3                        # case 3
const/16 v0, 0x14
goto :goto_0

:goto_0                           # switch 结束
return-void

:pswitch_data_0                   # 跳转表开始
.packed-switch 0x0                # 从 0 开始
    :pswitch_0
    :pswitch_1
    :pswitch_2
    :pswitch_3
.end packed-switch                # 跳转表结束
```

对于非递增的switch，代码如下

```smali
int a = 10;
switch (a){
    case 0:
        a = 1;
        break;
    case 10:
        a = 5;
        break;
    case 20:
        a = 10;
        break;
    case 30:
        a = 20;
        break;
}
```

对应的smali如下

```smali
const/16 v0, 0xa

sparse-switch v0, :sswitch_data_0 # switch 开始

:sswitch_0                        # case 0
const/4 v0, 0x1
goto :goto_0

:sswitch_1                        # case 10
const/4 v0, 0x5

goto :goto_0

:sswitch_2                        # case 20
const/16 v0, 0xa
goto :goto_0

:sswitch_3                        # case 15
const/16 v0, 0x14
goto :goto_0

:goto_0                           # switch 结束
return-void

.line 55
:sswitch_data_0                   # 跳转表开始
.sparse-switch
    0x0 -> :sswitch_0
    0xa -> :sswitch_1
    0x14 -> :sswitch_2
    0x1e -> :sswitch_3
.end sparse-switch                # 跳转表结束
```

### 比较指令

比较指令实现了对两个寄存器的值（浮点型或长整型）进行比较的操作。

其格式为cmp(l/g)-kind vAA, vBB, vCC，其中vBB寄存器与vCC寄存器是需要比较的两个寄存器或寄存器对，比较的结果放到vAA寄存器。

- l-->less
- g--> great

目前的比较指令如下

| **指令**      | **说明**                                   |
| ----------- | ---------------------------------------- |
| cmpl-float  | 比较两个单精度浮点数。如果vBB寄存器大于vCC寄存器，结果为-1，相等则结果为0，小于的话结果为1 |
| cmpg-float  | 比较两个单精度浮点数。如果vBB寄存器大于vCC寄存器，则结果为1，相等则结果为0，小于的话结果为-1 |
| cmpl-double | 比较两个双精度浮点数。如果vBB寄存器对大于vCC寄存器对，则结果为-1，相等则结果为0，小于则结果为1 |
| cmpg-double | 比较两个双精度浮点数。如果vBB寄存器对大于vCC寄存器对，则结果为1，相等则结果为0，小于的话，则结果为-1 |
| cmp-long    | 比较两个长整型数。如果vBB寄存器大于vCC寄存器，则结果为1，相等则结果为0，小则结果为-1 |

### 字段操作指令

> TODO 补充。fei chong

字段操作指令主要是对实例的字段进行读写操作。其中读操作使用get来标记，即vx=vy.field。写操作使用put来标记，即vy.field=vx。

其中对于java中的类来说，主要分为两种字段，普通字段，静态字段。对于普通字段采用操作指令前加i来标记，如iget，iput。对于静态字段采用在操作指令前加s来标记，如sput，sget。

此外，对于不同字段大小的操作会在指令的后面加上后缀来进行区别。如 iget-byte指令表示读取类型为字节的实例字段的值，iput-short指令表示设置的实例字段的类型为短整型。

普通字段操作指令有：

iget，iget-wide，iget-object，iget-boolean，iget-byte，iget-char，iget-short，

iput，iput-wide，iput-object，iput-boolean，iput-byte，iput-char，iput-short。

静态字段操作指令有：

sget，sget-wide，sget-object，sget-boolean，sget-byte，sget-char，sget-short，

sput，sput-wide，sput-object，sput-boolean，sput-byte，sput-char，sput-short。

如果我们编写如下代码

```java
int[] arr = new int[2];
int b = arr[0];
arr[1] = b;
```

其对应的smali如下

```smali
const/4 v0, 0x2
new-array v1, v0, I
const/4 v0, 0x0
aget-int v2, v1, v0
const/4 v0, 0x1
aput-int v2, v1, v0
```

如果我们想获得类com.example.test的静态int类型的字段staticField，其smali如下

```smali
sget v0, Lcom/example/Test;->staticField:I
```


### 方法调用指令
> TODO 补充。fei chong

方法调用指令实现了调用实例的方法的操作。其基础为invoke，在其基础上会根据调用方法的类别不同，如虚方法，父类方法等添加后缀，最后会选择性地使用range来指定寄存器范围。一般来说会分为两类

- invoke-kind {vC, vD, vE, vF, vG},meth@BBBB

- invoke-kind/range {vCCCC  .. vNNNN},meth@BBBB两类


  总体来说，一般有如下指令

| **指令**                                   | **说明**    |
| ---------------------------------------- | --------- |
| invoke-virtual 或 invoke-virtual/range    | 调用实例的虚方法  |
| invoke-super 或 invoke-super/range        | 调用实例的父类方法 |
| invoke-direct 或 invoke-direct/range      | 调用实例的直接方法 |
| invoke-static 或 invoke-static/range      | 调用实例的静态方法 |
| invoke-interface 或 invoke-interface/range | 调用实例的接口方法 |

Dalvik中直接方法是指类的所有实例构造器和`private`实例方法，对于`protected`或者`public`方法都叫做虚方法。


### 数据转换指令

> TODO 补充。fei chong

数据转换指令主要是将一种数据类型转换为另一种数据类型。目前已有的指令如下

| **指令**          | **说明**            |
| --------------- | ----------------- |
| neg-int         | 对整型数求补            |
| not-int         | 对整型数求反            |
| neg-long        | 对长整型数求补           |
| not-long        | 对长整型数求反           |
| neg-float       | 对单精度浮点型数求补        |
| neg-double      | 对双精度浮点型数求补        |
| int-to-long     | 将整型数转换为长整型        |
| int-to-float    | 将整型数转换为单精度浮点型数    |
| int-to-dobule   | 将整型数转换为双精度浮点数     |
| long-to-int     | 将长整型数转换为整型        |
| long-to-float   | 将长整型数转换为单精度浮点型    |
| long-to-double  | 将长整型数转换为双精度浮点型    |
| float-to-int    | 将单精度浮点数转换为整型      |
| float-to-long   | 将单精度浮点数转换为长整型数    |
| float-to-double | 将单精度浮点数转换为双精度浮点型数 |
| double-to-int   | 将双精度浮点数转换为整型      |
| double-to-long  | 将双精度浮点数转换为长整型     |
| double-to-float | 将双精度浮点数转换为单精度浮点型  |
| int-to-byte     | 将整型转换为字节型         |
| int-to-char     | 将整型转换为字符型         |
| int-to-short    | 将整型转换为短整型         |

举个例子`int-to-short v0,v1` 即将寄存器v1的值强制转换为short类型，并放入v0中。

### 数据运算指令

> TODO 补充。fei chong

数学算指令包括算术运算指令与逻辑运算指令。其中，算术运算指令包括加，减，乘，除，模，移位等运算，逻辑运算指令主要进行数值间与，或，非，抑或等运算。

数据运算指令有以下四类，其中运算符为binop。

| **指令**                     | **说明**                         |
| -------------------------- | ------------------------------ |
| binop vAA, vBB, vCC        | 将vBB寄存器与vCC寄存器进行运算，结果保存到vAA寄存器 |
| binop/2addr vA, vB         | 将vA寄存器与vB寄存器进行运算，结果保存到vA寄存器    |
| binop/lit16 vA, vB, #+CCCC | 将vB寄存器与常量 CCCC进行运算，结果保存到vA寄存器  |
| binop/lit8 vAA, vBB, #+CC  | 将vBB寄存器与常量CC进行运算，结果保存到vAA寄存器   |

后面3类指令比第1类指令分别多出了2addr，lit16，lit8后缀。但是，对于基础字节码相同的指令来说，其执行的运算操作是类似的。所以这里我们主要介绍第一类指令。除此之外，根据数据的类型不同会在基础字节码后面加上数据类型后缀，如`-int` 或 `-long` 分别表示操作的数据类型为整型与长整型。第一类指令的运算类型如下

| 运算类型      | **说明**             |
| --------- | ------------------ |
| add-type  | vBB + vCC          |
| sub-type  | vBB - vCC          |
| mul-type  | vBB * vCC          |
| div-type  | vBB / vCC          |
| rem-type  | vBB % vCC          |
| and-type  | vBB & vCC          |
| or-type   | vBB \| vCC         |
| xor-type  | vBB ^ vCC          |
| shl-type  | vBB << vCC ，有符号数左移 |
| shr-type  | vBB >> vCC，有符号数右移  |
| ushr-type | vBB >>> vCC，无符号数右移 |

其中基础字节码后面的-type可以是-int，-long， -float，-double。

举个例子，java源码为

```java
int a = 5, b = 2;
a += b;
a -= b;
a *= b;
a /= b;
a %= b;
a &= b;
a |= b;
a ^= b;
a <<= b;
a >>= b;
a >>>= b;
```

其对应的smali为

```smali
const/4 v0, 0x5
const/4 v1, 0x2
add-int/2addr v0, v1
sub-int/2addr v0, v1
mul-int/2addr v0, v1
div-int/2addr v0, v1
rem-int/2addr v0, v1
and-int/2addr v0, v1
or-int/2addr v0, v1
xor-int/2addr v0, v1
shl-int/2addr v0, v1
shr-int/2addr v0, v1
ushr-int/2addr v0, v1
```

## 详解smali文件

### Smali文件格式

在你可以在一个xxx.java中定义多个类（包括匿名内部类），但一个smali文件只能定义一个类，一般格式是：
```smali
.class 修饰符 类名
.super 父类的类名
.source 源文件名

{实现的接口}

{注解列表}

{字段列表}

{方法列表}
```
1、其中修饰符就是public、private、protected、static和final等，和Java中的差不多，另外对于类还有interface和enum来表示这个类是一个接口或者枚举类；

2、Smali中的类名都是L包名路径/类名;，例如Android中的TextView类，它的包名是android.widget，如果你要在Smali中表示这个类，就要写成Landroid/widget/TextView;

3、源文件名就是编译这个类的java文件名，如Main.java，仅用于debug删了也没影响；

4、接口的语法是：
.implements 接口类名
可以有0个或者多个，表示这个类实现了哪些接口；

5、注解的话就是Java代码中@XXX之类的代码，例如比较常见的 @Override、 @Nullable和@NonNull，它的 Smali 语法是：
.annotation xxxxxxx
    xxxxxx
.end annotation
如果你不知道注解是干嘛用的也没关系，反正一般情况也用不上，只要在Smali中看到annotation时知道它是注解就行了；

6、声明的字段（field），方法就是method，下次会详细讲讲。

比较有意思的是，Smali 代码基本上还原了 Java 代码中含义。它主要有以下两种类型的语句：

- 声明语句用来声明 java 中自顶向下的类，方法，变量类型，以及每个方法中所要使用的寄存器的个数等信息。
- 执行语句来执行 java 中的每一行代码，包含方法的调用，字段的读写，异常的捕捉等操作。


## 声明语句

在 smali 代码中，声明语句一般都是以 `.` 开始。

----




<details markdown='1'><summary>展开/收起</summary>


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
  
</details>
  
 


----

References

* [教你读懂Smali代码（三）](https://bbs.binmt.cc/thread-1266-1-1.html)
* [教你读懂Smali代码（一）](https://bbs.binmt.cc/thread-1205-1-1.html)
* [教你读懂Smali代码（二）](https://bbs.binmt.cc/thread-1206-1-1.html)
* [教你读懂Smali代码（四）](https://bbs.binmt.cc/thread-1640-1-1.html)
* [深入理解Dalvik字节码指令及Smali文件][深入理解Dalvik字节码指令及Smali文件]
* [Home · JesusFreke/smali Wiki (github.com)](https://github.com/JesusFreke/smali/wiki)
* [ruanyf/document-style-guide: 中文技术文档的写作规范 (github.com)](https://github.com/ruanyf/document-style-guide)
* [非虫 《Android软件安全与逆向分析》][非虫 《Android软件安全与逆向分析》]
* [basic_operating_mechanism](https://ctf-wiki.org/android/basic_operating_mechanism/java_layer/smali/smali)
  * [basic_operating_mechanism](https://github.com/ctf-wiki/ctf-wiki/tree/master/docs/zh/docs/android)
* [Android逆向基础：Smali语法](https://www.jianshu.com/p/9931a1e77066)
* [Android 逆向之 smali](http://wossoneri.github.io/2019/09/12/[Android][Security]Decompile-smali/)
* [Smali 语法解析——Hello World](https://juejin.cn/post/6844903732774174734)
* [What is Smali Code Android](https://stackoverflow.com/questions/30837450/what-is-smali-code-android)
* [smali-assembler-for-dalvik](https://mobsecguys.medium.com/smali-assembler-for-dalvik-e37c8eed22f9)
* [Smali Introduction Manual](https://programmer.help/blogs/smali-introduction-manual.html)
* [安卓逆向系列教程（一）Dalvik 指令集](https://github.com/jsonhui/fl-android-re-tut/blob/master/1.md) by [飞龙](https://github.com/wizardforcel)
* [smali](https://github.com/HelloHuDi/AndroidReverseNotes/blob/master/smali.md)
* [吾爱破解安卓逆向入门教程--导航帖（2018-06）](https://www.52pojie.cn/thread-408645-1-1.html)


[非虫 《Android软件安全与逆向分析》]: https://douban.com/book/subject/20556210/
[深入理解Dalvik字节码指令及Smali文件]: https://blog.csdn.net/dd864140130/article/details/52076515
[Dalvik 字节码]:[https://source.android.google.cn/devices/tech/dalvik/dalvik-bytecode.html]

本文部分图片来自 网络
