# 专业课
## 计网

## 操作系统
### 南大OS笔记
**操作系统给你编程的全部**
我们所用的语言都是Turing complete的，但自己却编不出程序，而学好《操作系统》则可以具备编写一切“能写出来的”程序的能力（悟性好的）

> 充满热情而且相当聪明的学生...早就听说过物理学如何有趣...相对论、量子力学......但是，当他们学完两年以前那种课程后，许多人就泄气了......学的还是斜面、静电这样的内容
> — — 《The Feynman Lectures on Physics, 1963》

做一个很‘酷’的人

**什么是操作系统**
> Operating System: A body of software, in fact, that is responsible for making it easy to run **programs** (even allowing you to seemingly run many at the same time), allowing programs to **share memory**, enabling programs to **interact with devices**, and other fun stuff like that. (OSTEP)

**问出正确的问题**
    操作系统如何从一开始变成现在这样的？（从简单到复杂）
重要线索：
1. 计算机（硬件）
2. 程序（软件）
3. 操作系统（管理软件的软件）


*当我们在谈论操作系统是什么时，我们在讨论操作系统的历史*

#### 操作系统的历史
##### 1950s的操作系统
早期计算机非常昂贵，但需求量又大，由此产生集中管理计算机的需求：**多用户排队共享计算机**

开始形成**操作系统**的概念：管理众多的任务，使计算机处理不同任务，即操作（operate）任务（jobs）的系统（system）

+ “批处理系统”=程序的自动切换（换卡）+ 库函数API
+ Disk Operating Systems(DOS)
    + 操作系统中开始出现“设备”、“文件”、“任务”等对象和API

我的理解：批处理系统就是对于送来的各种任务（需要执行的FORTRAN程序），执行完一个后切换到下一个，并且实现用户希望的（如把结果打孔到新的卡片上）功能，即库函数API。

另：这时的软件还是打孔程序。

> 所有概念的出现都是**自然**的。当被一个看不懂的抽象概念糊到脸上看不懂时，可以了解一下它产生的动机（motivation）

##### 1960s的计算机
1960s出现了更快更大的内存和更快的处理器（硬件的发展）

更大的内存意味着内存中可以放进更多的程序，即**同时将多个程序载入内存**（Multipleprogram）

+ 有了进程（process）的概念
+ 进程在执行I/O时，可以将CPU让给另一个进程
    1. 在多个地址空间隔离的程序之间切换
    2. 虚拟存储是一个程序出bug不会crash整个系统

操作系统中自然地增加了进程管理API。

一个进程可能就是一个待执行的任务，在这个任务需要放进I/O设备这样的外部设备（external device）时，CPU空闲，则操作系统可以暂时保存这个任务的状态，然后令另一个任务进入CPU去执行。
即**程序之间的切换**

由上述想法延伸出定时切换，即中断机制

+ 时钟中断
+ 调度策略

这时也出现了**Multics**(MIT, 1965)

此后计算机快速发展，个人计算机PC普及，其功能几乎与今天无异

##### 1970s+的操作系统
分时系统走向成熟，UNIX诞生

> UNIX的重要发明：
> 
    1973: 信号 API、管道 (对象)、grep (应用程序)
    1983: BSD socket (对象)
    1984: procfs (对象)……
> UNIX 衍生出的大家族
>
> 1BSD (1977), **GNU** (1983), **MacOS** (1984), 
> 
> AIX (1986), Minix (1987), **Windows** (1985), 
> 
> **Linux 0.01** (1991), Windows NT (1993), Debian (1996),
>  
> **Windows XP** (2002), **Ubuntu** (2004), **iOS** (2007),
>  
> **Android** (2008), Windows 10 (2015), ……

##### 现代操作系统
> 通过**虚拟化**硬件资源为程序运行提供服务的软件

空前复杂的系统（之一）

##### 三个根本问题

**操作系统服务谁**？

    程序 = 状态机
    课程涉及：多线程 Linux 应用程序

状态机含内存和寄存器，其随程序执行而变化，这就是研究的第一个问题

(设计/应用视角) **操作系统为程序提供什么服务**？

    操作系统 = 对象 + API
    课程涉及：POSIX + 部分 Linux 特性

(实现/硬件视角) **如何实现操作系统提供的服务**？

    操作系统 = C 程序
        完成初始化后就成为 interrupt/trap/fault handler
    课程涉及：xv6, 自制迷你操作系统

#### Prerequisites
计算机专业学生必须具备的核心素质


> **是一个合格的操作系统用户**
> 
> + 会 STFW/RTFM 自己动手解决问题
> + 不怕使用任何命令行工具
>       + vim, tmux, grep, gcc, binutils, ...
> 
>**不惧怕写代码**
>
> + 能管理一定规模 (数千行) 的代码
> + 能在出 bug 时默念 “机器永远是对的、我肯定能调出来的”
>       + 然后开始用正确的工具/方法调试
>        
>给 “学渣” 们的贴心提示：补基础、补基础、补基础           

**Talk is Cheap. Show Me the Code!**

> 应用视角/操作系统设计：操作系统 = 对象 + API
> 
>   + demo 小程序 (x86-64 为主)
>   + 各类系统工具的实现 (strace, gdb, ...)
> 
> 硬件视角/操作系统实现：操作系统 = C 程序
> 
>   + xv6
>       + 2006 年 Russ Cox, Frans Kaashoek, Robert Morris 在 MIT 重写的 UNIX 系统
>       + 大家熟悉的 RISC-V 版本
>   + Abstract Machine
>       + 2017 年为 Project-N 设计的抽象层
>       + 在《计算机系统基础》中已经使用过

**最重要的：Get Your Hands Dirty**

> 应用视角 (设计)：Mini Labs x 6
> 
> + 使用 OS API 实现 “黑科技” 代码
> 
> 硬件视角 (实现)：OS Labs x 5
> 
> + 自己动手实现一个真正的操作系统
>
> 全部 Online Judge
> 
> + 代码不规范 → -Wall -Werror 编译出错
> + 代码不可移植 → 编译/运行时出错：int x = (int)&y;
> + 硬编码路径/文件名 → 运行时出错：open("/home/a/b", ...)


但是太难了，似乎需要**计算机系统基础**的先导知识，先缓缓


## Python数据处理

## 编译原理

## 汇编