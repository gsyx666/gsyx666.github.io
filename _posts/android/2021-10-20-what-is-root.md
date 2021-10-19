对于搞机党或者开发人员来说，root 一定是一个不陌生的名词。在 [当我们谈论解锁 BootLoader 时，我们在谈论什么？] 一文中我们了解到，解锁 Bootloader 实际上能做到的是让手机可以运行第三方的操作系统，而通常来说，我们给手机解锁 Bootloader 就是为了获取 Root 权限。那么，何为 root?，解锁 Bootloader 和 root 到底有什么联系和区别？

> In Unix-like computer OSes (such as Linux), root is the conventional name of the user who has all rights or permissions (to all files and programs) in all modes (single- or multi-user).

维基百科说，在类 Unix 系统中，root 是在所有模式（单用户或多用户）下对所有文件和程序拥有所有权利或许可的用户的名称。

现代操作系统（本文主要讨论 Android 系统，下同）一般都是多用户的，那个名为 root 的用户所拥有的权限就是 root 权限；而 root 权限中有三个「所有」，可以简单这么理解：root 意味着最高权限；不过，这么描述不够具象，接下来就带大家了解一下 root 的方方面面。

### root 的来源
在类 Unix 系统中， 一切皆文件。而这些文件通常以一个分层的树形结构在文件系统中呈现，每一个文件都有一个父目录，而那个最顶层的父目录被称之为根目录(root directory)；root 用户之所以被称之为 root，大抵是因为它是唯一能修改 root directory 的用户。

因为 root 用户拥有最高权限，因此它也通常被称之为超级用户(superuser)；在类 Unix 系统中，每一个用户都有一个 ID，root 用户的 ID 是 0，从传统意义上讲，uid 为 0 就是 root 用户，也就拥有最高权限。

### 最高权限具体指的哪些？
我们一直在说，「最高权限」，那么最高权限到底是哪些呢？

直白点来说，手机是由多个零部件组成的，比如说，CPU、内存、闪存、各种硬件设备（如相机，屏幕、传感器等），所谓最高权限，就是对所有这些设备的控制权。

最高权限具体指的哪些？
我们一直在说，「最高权限」，那么最高权限到底是哪些呢？

直白点来说，手机是由多个零部件组成的，比如说，CPU、内存、闪存、各种硬件设备（如相机，屏幕、传感器等），所谓最高权限，就是对所有这些设备的控制权。

对于 CPU 来说，现在的 CPU 芯片一般都有不同的特权等级，这些不同的等级可以执行不同的指令。就拿 AArch64 构架来说，CPU 有四个特权等级，EL0 ~ EL3：


