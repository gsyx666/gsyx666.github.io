---

layout:     post   				    # 使用的布局（不需要改）
title:      教你读懂Smali代码（三） 				# 标题 
subtitle:   Hello Android #副标题
date:       2020-03-19 				# 时间
author:     BY bin 						# 作者
hidden: true
header-img: img/post-bg-2015.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Android 逆向
    - 转载
---

> 本文转载自[MT论坛bin](https://bbs.binmt.cc/thread-1266-1-1.html)


# 寄存器

相信大家在看Smali时注意到了有很多v0、v1、v2、p0、p1、p2之类的标识符，这些都代表了寄存器。

那么什么是寄存器呢？你可以把它认为是变量，或者是暂时存放东西的地方。

举个例子：

有一个**静态方法abc(String)**，如果你要在Java方法中调用这个方法，直接输入abc("Hello");就行了。

而在Smali中，你不能直接把字符串参数传递给方法，你需要一个寄存器（比如v0），先把"Hello"放到v0中，然后再调用abc方法，并告诉它你需要的参数在v0里面，自己去拿吧。
```smali
#定义一个字符串常量"Hello"放到v0中
const-string v0, "Hello"

#调用abc方法，需要的参数放在v0中 
 invoke-static {v0}, LXX;->abc(Ljava/lang/String;)V
```
现在大家理解什么是寄存器了吧。

另外寄存器v0、v1、v2后面的数字也不是随便写的，需要在方法的开头用.registers N来指定寄存器的数量，然后才可以使用寄存器v0到v(N-1)。


## 参数寄存器

上面说的都是普通寄存器vN，另外Smali还特意定义了一种参数寄存器pN，用于存放这个方法传入的参数的值。

如果一个方法有n个寄存器，有m个参数，那么n必须大于等于m，并且n个寄存器的后面m个是参数寄存器，举个例子：

某个静态方法abc(int, int, int)，它一共有3个参数，如果它一共有5个寄存器（通过.registers N定义，N不能小于3）。

|普通寄存器|对应参数寄存器|
|---|---|
|v0| |	
|v1| |	
|v2|p0|
|v3|p1|
|v4|p2|

当我调用abc(11, 22, 33)时，p0中的值初始化为11，p1中的值初始化为22，p2中的值初始化为33，v0和v1不会初始化。

|普通寄存器|参数寄存器|初始化|
|---|---|---|
|v0| | |
|v1| | |
|v2|p0|11|
|v3|p1|22|
|v4|p2|33|

当我把寄存器数量改成6（.registers 6），寄存器就会变成下表所示：

|普通寄存器|参数寄存器|初始化|
|---|---|---|
|v0| | |
v1| | |
v2| | |		
|v3|p0|11|
|v4|p1|22|
|v5|p2|33|

思考一下，如果不使用参数寄存器，代码中全部用vN，那么改变寄存器数量后，你还得改多少代码？

## 隐藏的参数

对于非静态方法，它的参数寄存器数量比实际参数多了一个，p0会固定用于表示当前类实例（Java中的this），从p1开始才是真正的参数，我们可以通过Java2Smali工具来验证一下，Java代码如下：

![](http://img04.sogoucdn.com/app/a/100520146/539b5a636ef27c32f447db462f7c7874)

test1()和test2()的唯一区别就是一个是静态一个非静态

test1()的Smali代码：

![](http://img04.sogoucdn.com/app/a/100520146/0febbc8bb9007c6bf0c7c85f02f4574f)

test2()的Smali代码：

![](http://img01.sogoucdn.com/app/a/100520146/56c606a0fd79ba48b6e1f72e3c0643b8)

两个方法都是依次打印出两个参数，test1()中24行是打印第一个参数用的是p0，29行是打印第二个参数用的是p1；对照下test2()中则分别用的是p1和p2。

那test2()中的p0真的代表this吗？我们也可以修改代码验证下：

![](https://oss.bbs.binmt.cc/image/000/00/25/74_600_1000.jpg?mobile=2)

![](https://oss.bbs.binmt.cc/image/000/00/25/75_600_1000.jpg?mobile=2)

到这边讲的都是基础知识，大家不懂的可以随时回复提问，下一篇开始讲代码了。
