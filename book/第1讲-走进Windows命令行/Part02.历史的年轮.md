# 第1讲-Part02.历史的年轮



</br>

</br>



## 一、操作系统杂谈之概念辨析（重要）



### 1、Dos和Windows系统



操作系统历史上到下（从古老到年轻）

| 操作系统                       | 描述                                                         |
| ------------------------------ | ------------------------------------------------------------ |
| Dos                            | 无图形界面，纯字符串，就像你在电影中看到的“骇客”用的电脑界面差不多（注意：黑客不等于骇客，媒体已经日常搞错这2个概念） |
| Windows 1.0                    | Dos上的一个图形界面 Windows 1.0 ，带画图、记事本等程序。一直发展到 Windows 3.1 （PS：Windows 3.1对应的中文版的版本号是3.2）。特点：在这个时候因为 DOS 总是作为 Windows 的基础运行的，在运行Windows 的时候当然可以回到 DOS 下运行 DOS 命令。 |
| Windows95                      | 划时代的 Windows 95，这个系统下它不是直接运行在 DOS 上，而是在 DOS 启动的时候直接跳到一Windows 图形界面。 Windows 95 上的程序是32位的，不过操作系统的核心还是 DOS 下的那一套，虽然图形方面当然是32位的，这个时候的 Windows 还是可以运行16位下的 DOS 程序。 |
| 3个版本                        | **Windows 95、 Windows 98 再接下来是 Windows ME ，这就是32位的仍然没有摆脱 DOS 的三个Windows 版本。** |
| Windows NT 3.5到**Windows7/8** | Windows NT 3.5，Windows NT 4.0，Windows 2000，Windows XP/Windows 2003 开始的这一代了，也包括 Windows 7 ，Windows 8 等，我们叫做 NT 内核的 Windows ，它的核心就完全是32位的，跟从前汇编编写的代码库完全告别了。这个时候操作系统只是在最初的时候从16位模式跳到32位的保护模式，除此之外不再真正有16位的代码，所以这个时候就没有运行 DOS 程序的条件了。 |
| **Windows10**                  | 现在除了cmd.exe之外还加入了powershell（对标Linux下的shell）  |





| 操作系统                                 | 带有的命令行工具    |
| ---------------------------------------- | ------------------- |
| Dos操作系统                              | Dos                 |
| WindowsXP，WindowsNT、Windows7、Windows8 | command             |
| Windows10                                | command、powershell |





> 高阶读者阅读：
>
> 本部分参照知乎：https://www.zhihu.com/question/24744565
>
> - 1、早期的 Windows 中就是 DOS 上的一个外壳
> - 2、中期的 Windows 和 DOS 共享了一些代码，在 Windows XP 中已经完全告别了 DOS ，只能靠模拟来运行这些DOS程序。不过，旧的DOS程序在 Windows XP 上还是可以照常运行，虽然有些比较依赖硬件的程序会运行不正常（不过这些程序反正换了一套硬件就很有可能运行不正常了）， Windows 8 在第一次运行 DOS 程序的时候会提示安装 NTVDM 。这个 NTVDM 就是 NT 内核 Windows 运行 DOS 程序的关键，它用来模拟 DOS 程序运行时所依赖的环境。不过以上这些都是说的32位 Windows ，在64位 Windows 中本身也没有 NTVDM 功能，所有也就运行不了 DOS 程序了。  
> - 3、不过最后还剩一个问题，在 Windows NT 中执行 DOS 命令到底是什么意思？  
>   DOS 上带有一系列的命令，早期和中期的 Windows 都可以执行这些 DOS 命令。到了 Windows NT ，这些命令的使用方式没有变，于是就**沿用了**执行 DOS 命令这个说法。而实际上在 Windows NT 中使用这些命令时都只是在使用一个叫 cmd.exe 的命令行辅助工具，跟 DOS 不再有什么关系了。  









</br>

### 2、命令行解释和批处理脚本



**（1）命令行解释器（Windows命令行交互）**

命令行解释器是一个单独的软件程序，它可以在用户和操作系统之间提供直接的通讯。（用户和操作系统之间！）
。通过使用类似于`MS-DOS`命令解释程序`Command.com`的单独字符，命令行解释器执行程序并在屏幕上显示其输出。
Windows 服务器操作系统命令行解释器使用命令解释程序`cmd.exe`（该程序加载应用程序并指导应用程序之间的信息流动）将用户输入转换为操作系统可理解的形式。

</br>

**（2）批处理脚本**

**批处理**，也称为批处理**脚本**，英文译为`batch`，批处理文件后缀`bat`就取的前三个字母（注意：<font style="background: yellow">批处理文件的扩展名是BAT或者CMD（不区分大小写）</font>）。  



> 批处理特点：
>
> 顾名思义，批处理就是对某对象进行批量的处理
>
> 1、把任何一批命令放在有这样扩展名的文件里，执行的时候就会一条一条的执行完，当然我们还可以在其中加入一些逻辑判断的语句，让里面的命令在满足一定条件时执行指定的命令。（`Batch脚本之于如今的Windows类似于shell脚本之于Linux`）
>
> 2、语法：
> 它的构成没有固定格式，只要遵守以下这条就ok了：
>
> 1）每一行可视为一个命令，每个命令里可以含多条子命令
>
> 2）从第一行开始执行，直到最后一行结束
>
> 3）批处理有一个很鲜明的特点：
> 使用方便、灵活，功能强大，自动化程度高。
> 实现自动化办公









</br>

</br>

## 二、操作系统中Superman



你以为操作系统中有这个？

![Superman01](.\img\Superman01.jpg)

还是这个？

![Superman01](.\img\Superman02.jpg)

还是这个？

![Superman01](.\img\Superman03.jpg)



No，No，No都不是:smirk::smirk::smirk:

操作系统中的超人，其实就是管理员，后面我们的教程中会涉及到一些普通的用户无法使用的命令，因而我们在这提前告知一些打开管理员权限的方式:smile:

> 高阶读者：
>
> 就像Linux操作系统一样。在Windows下超人一般的管理员



### 1、Windows命令行普通和root打开方式

##### （1）管理员权限



##### （2）普通权限

快捷键『windows+R』然后在弹出的窗口中输入cmd

![cmd](.\img\cmd.png)





### 2、PowerShell普通和root打开方式

测试环境Windows10

##### （1）管理员权限

快捷键『windows+X』然后按下『A』

![PowerShell_root](.\img\PowerShell_root.png)



##### （2）普通权限

快捷键『windows+X』然后按下『I』

![PowerShell](.\img\PowerShell.png)



</br>

</br>

## 三、高阶读者加餐

> 高阶读者加餐    
> 目前比较常见的批处理包含两类：**DOS批处理**和**PS批处理**  
> 1、PS批处理是基于强大的图片编辑软件Photoshop的，用来批量处理图片的脚本  
> 2、DOS批处理则是基于DOS命令的，用来自动地批量地执行DOS命令以实现特定操作的脚本。本教程讲的就是DOS批处理  
> 3、批处理是一种简化的脚本语言（所以你看它的语法，和Linux下的shell脚本，或者Python这种脚本语言类似），它应用于DOS和Windows系统中，它是由DOS或者Windows系统内嵌的命令解释器（通常是COMMAND.COM或者CMD.EXE）解释运行。类似于Unix中的Shell脚本  
> 4、其最简单的例子，是逐行书写在命令行中会用到的各种命令。更复杂的情况，需要使用if，for，goto等命令控制程序的运行过程，如同C，Basic等高级语言一样。如果需要实现更复杂的应用，利用外部程序是必要的，这包括系统本身提供的外部命令和第三方提供的工具或者软件  
> 5、批处理文件，或称为批处理程序，是由一条条的DOS命令组成的普通文本文件，可以用记事本直接编辑或用DOS命令创建，也可以用DOS下的文本编辑器Edit.exe来编辑  
> 6、系统在解释运行批处理程序时，首先扫描整个批处理程序，然后从第一行代码开始向下逐句执行所有的命令，直至程序结尾或遇见exit命令或出错意外退出  
> 7、在“命令提示”下键入批处理文件的名称，或者双击该批处理文件，系统就会调用Cmd.exe运行该批处理程序。一般情况下，每条命令占据一行；当然也可以将多条命令用特定符号（如：&、&&、|、||等）分隔后写入同一行中；还有的情况就是像if、for等较高级的命令则要占据几行甚至几十几百行的空间  