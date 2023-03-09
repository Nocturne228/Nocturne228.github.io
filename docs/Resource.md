# 资源

这里存放在互联网各处看到的好的资料与网站以及学到的小知识（当然更多的在我硬盘里）

## 数学

这篇文章对“Mathematical Maturity”做出了一些解释

+ [Precise Definitions of Mathematical Maturity](https://blogs.ams.org/matheducation/2019/04/15/precise-definitions-of-mathematical-maturity/)

## 计算机

### The Missing Semester

MIT的神课[The Missing Semester of Your CS Education](https://missing.csail.mit.edu/)

前三讲关于终端的知识：
[The Missing Semester 第1讲 - 课程概览与 Shell](https://www.bilibili.com/video/BV1Eo4y1d7KZ/?vd_source=0024ced12c6d4e5a148189fa2eb49dd9)
[The Missing Semester 第2讲 - Shell 工具和脚本](https://www.bilibili.com/video/BV1Vv411v7FR/?spm_id_from=333.788.recommend_more_video.-1&vd_source=0024ced12c6d4e5a148189fa2eb49dd9)
[The Missing Semester 第3讲 - 编辑器 (Vim)](https://www.bilibili.com/video/BV1Dy4y1a7BW/?spm_id_from=333.788.recommend_more_video.-1&vd_source=0024ced12c6d4e5a148189fa2eb49dd9)

### 南大SICP

#### lab0: Getting Started

+ Terminal

终端在早期是 *能够将使用者的输入传输进计算机、显示计算机的输出、并支持光标控制等多项任务* 的硬件设备。最著名的如VT100是一种具有显示器的终端。

拥有图形界面的操作系统流行后，显示器用来显示图形界面，终端则以硬件模拟器（terminal emulator）的方式存在

    操作系统为用户提供了一个“交互界面”，这个程序（软件）叫做壳层（shell）。
    在Windows中，图形用户界面由explorer.exe提供，命令行界面由powershell.exe或cmd.exe提供。
    在Unix系统中，命令行界面有sh、bash、zsh、fish等多种实现。
    未来我们提及终端的时候，更多指的是终端模拟器外加上操作系统壳层程序所组成的整体。

不同终端的显示方式不同，但提示符（prompt）的组成大体一致

下面示例都是我的个人电脑上所显示的内容

以Windows为例：

`PS D:\Users\hp>`

prompt由以下三部分组成

+ 其中`PS` 表示当前终端使用Powershell
+ `D:\Users\hp` 表示终端的 **当前工作目录** ，这个概念在使用git时非常重要
+ `>` 提示可以在它之后输入命令了（后面闪烁着光标）

再以git bash为例：

`hp@xiaoma-victus MSYS ~ (main) $`

+ `hp@xiaoma-victus` 表示当前用户名
+ `MSYS ~` 表示当前工作目录（具体路径地址会显示在标题栏`MSYS:/c/Users/hp`）
+ `(main)` 是分支（或许？）

> `~`是什么？
>
> 部分shell程序提供[波浪号扩展（Tilde Expansion）](https://www.gnu.org/software/bash/manual/html_node/Tilde-Expansion.html)的功能，~将被展开成环境变量$HOME，也就是用户的“家目录”，类似于Windows的C:\User\YOURNAME。
>
> 在以后的课程讲义和各类沟通交流中，我们应当**避免使用图片**来显示命令的运行结果，倾向于使用文本的方式来进行展示。 
> 根据习惯，我们使用$这一简短的符号来代替原本图片中一长串的提示符。

+ 工作目录的切换

如果遭遇报错：
``` cmd
$ python3 hello.py
python: can't open file 'hello.py': [Errno 2] No such file or directory.
```

说明“当前工作目录”中没有`hello.py`文件

这时我们需要`cd`命令来切换终端的当前工作目录

> cd的全称是change directory

    像D:\SICP\lab00以盘符（C盘的盘符叫做C:，D盘的盘符叫做D:，以此类推）开头的路径，就叫做绝对路径。否则叫相对路径。

    在macOS和Linux中并不存在“盘符”的概念，在这些操作系统中，最底层的文件夹叫做“根目录”（/，也就是“root”），以/开头的路径叫做绝对路径，如/home/user/sicp/lab00。

    你可能会注意到，Windows上路径的目录之间使用\分割，而macOS和Linux则使用/分割。

在表示目录时，`..`表示上一级目录；`.`表示当前目录

Windows中可以用`ls`或`dir`命令来显示当前目录下的文件



### 操作系统

南大OS课的前置课程ICS的PA(Progeamming Assignment)，最好先读完

+ [南京大学 计算机科学与技术系 计算机系统基础 课程实验 2022](https://nju-projectn.github.io/ics-pa-gitbook/ics2022/index.html)



从零开始学Linux（真的吗，我不信）

+ [Linux From Scratch](https://linuxfromscratch.org/)

初学Unix和Linux

+ [Harley Hahn's Guide to Unix and Linux](http://www.harley.com/books/sg3.html)

+ [Operating Systems: Three Easy Pieces](https://pages.cs.wisc.edu/~remzi/OSTEP/)

+ [GDB: The GNU Project Debugger](https://sourceware.org/gdb/documentation/)

### 编译

+ [GCC online documentation](https://gcc.gnu.org/onlinedocs/)

+ [GNU make](https://www.gnu.org/software/make/manual/html_node/index.html)

### 网页

+ [Documentation for binutils 2.40](https://sourceware.org/binutils/docs/)

### git

+ [Learn Git](https://www.atlassian.com/git)

### 其他

+ [The Art Of Command Line](https://github.com/jlevy/the-art-of-command-line)

+ [Bash Reference Manual](https://www.gnu.org/software/bash/manual/html_node/index.html)