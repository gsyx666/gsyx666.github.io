---

layout:     post   				    # 使用的布局（不需要改）
title:      教你读懂Smali代码（四） 				# 标题 
subtitle:   Teach you to read Smali code (IV) #副标题
hidden: true
date:       2020-03-19 				# 时间
author:     BY bin 						# 作者
header-img: img/post-bg-2015.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Android 逆向
    - 转载
    - Smali
---

> 本文转载自[MT论坛bin](https://bbs.binmt.cc/thread-1640-1-1.html)

# Android 逆向


## 调用方法

Smali语法中调用方法的指令一共有5条，分别是：

|指令名称|含义|
|---|---|
|invoke-virtual|调用虚方法|
|invoke-direct|直接调用方法|
|invoke-static|调用静态方法|
|invoke-super|调用父类方法|
|invoke-interface|调用接口方法|

使用语法是：**invoke-xxxxxx {参数列表}, 类名->方法名(参数类型)返回类型**

所以当你在Smali代码中看到invoke开头的指令，就可以直接确定这句代码用于调用某个方法，至于invoke-后面跟着的单词，取决于它要调用的方法的类型。

### 调用虚方法

虚方法其实是Java多态中的一个概念，大家应该知道Java中子类可以重写父类中可被继承的非final方法，调用这些方法时，都需要使用invoke-virtual指令，才能实现多态的特性，例如下面代码：
```smali
Object obj = "123";
obj.equals("456");
```

这边调用equals方法的Smali代码是：
```smali
invoke-virtual {v0, v1}, Ljava/lang/Object;->equals(Ljava/lang/Object;)Z
```

表面上看是调用Object的equals方法，但是由于obj实际上是字符串“123”，而字符串类String中重写了equals方法，所以虚拟机最后调用的是String的equals方法。

### 直接调用方法

由于调用虚方法时，虚拟机需要先查找该方法是否被重写，而对于那些无法被重写的方法，查找显得是在浪费时间，所以使用invoke-direct指令来提高效率，其通常用于final方法、private方法、构造方法。

### 调用静态方法

这个没什么好说的，调用static方法时，就使用invoke-static。

### 调用父类方法

在子类中，如果它已经重写了父类的XX方法，而又想调用父类的XX方法时，可通过super.XX()来调用，其对于的指令就是invoke-super。

### 调用接口方法

这个很好理解，invoke-xxxxxx {参数列表}, 类名->方法名(参数类型)返回类型，如果类名对应的类是个接口，那么xxxxxx就得写interface。

### 补充

上面的5条指令都有对应的range扩展指令，也就是：invoke-virtual/range、invoke-direct/range等。

使用语法是：invoke-xxxxxx/range {vN...vM}, 类名->方法名(参数类型)返回类型，其中N小于M。

其等价于：invoke-xxxxxx{vN, vN+1,vN+2, ..., vM-2, vM-1, vM}, 类名->方法名(参数类型)返回类型。

一般只会对拥有很多个参数的方法使用range指令，来减少生成的代码体积以及提高运行效率。
