# 第2讲Part04.批处理中的19个特殊符号

> 符号列表
>
> | 符号 | 符号名称 |
> | ---- | -------- |
> | `@`  | 艾特     |
> | `&`  |          |
> | `&&` |          |
> | \|   |          |
> | \|\| |          |
> | `>`  |          |
> | `>>` |          |
> | `<`  |          |
> | `^`  |          |
> | `%`  |          |
> | `*`  |          |
> | `?`  |          |
> | `.`  |          |
> | `..` |          |
> | `""` | 双引号   |
> | `:`  | 冒号     |
> | `,`  | 逗号     |
> | `;`  | 分号     |
> | `::` |          |
>
> 







#### 1）@

隐藏执行的命令，只显示结果。

例子：
```bat
echo 你好
@echo 你好
pause
```

这个字符在批处理中的意思是关闭当前行的回显。

应用：`echo off`可以关闭掉整个批处理命令的回显，
但不能关掉echo off这个命令，现在我们在echo off这个命令前加个@
就可以**达到所有命令均不回显的要求**


```
rem 1.bat
echo off
dir d:\
pause
```

```
rem 2.bat
@echo off
dir d:\
pause
```




#### 2）&

>- 命令连接符号，就是将两个命令连续执行，不用分行
这个符号允许在一行中使用2个以上不同的命令。
当第一个命令执行失败了，也不影响后边的命令执行。

例子：
```bat
dir c:\ & dir d:\ & dir e:\
```





#### 3）&&
连接两个命令，当&&前的命令成功时，才执行&&后的命令

例子：
```bat
dir c:\ && dir d:\
dir z:\ && dir d:\
```





#### 4）|
管道符号，就是将上一个命令的输出的内容，作为下一个命令的输入内容

例子：
```bat
netstat -an | find "135"
```

例子:
```bat
type c:\windows\*.log|more
```

例如：
```bat
dir c:\|find "txt"
```

以上命令是：查找C：\所有，并发现TXT字符串。
FIND的功能请用 FIND /? 自行查看

在不使format的自动格式化参数时，我是这样来自动格式化A盘的

```bat
echo y|format a: /s /q /v:system
```

用过format的都知道，在格盘时要输入y来确认是否格盘，
这个命令前加上echo y并用|字符来将echo y的结果传给format命令

从而达到自动输入y的目的

（这条命令有危害性，测试时请慎重）






#### 5、||
命令连接符号，表示上一条命令执行失败后，才执行||符号后的内容

例子：
```bat
dir z: || dir c:\
```








#### 6、>
重定向符号，将命令的输出结果重定向到其后面的设备中去，后面的设备中的内容被覆盖
这个字符的意思是传递并且覆盖，他所起的作用是将运行的回显结果
传递到后面的范围（后边可以是文件，也可以是默认的系统控制台）

例子：
```bat
dir c:\ >d:\test.txt
```









#### 7、>>
重定向符号，将命令的输出结果重定向到其后面的设备中去，后面的设备中的内容会被增加在后面

例子：
```bat
dir c:\ >>d:\test.txt
dir d:\ >>d:\test.txt
```


补充一个：
<
重定向符,将后面的指定设备的内容,作为前面命令的输入内容

例子:
建立个1.txt文件,内容为net user

nc -v -e cmd.exe -t -l -p 888
nc 192.168.18.5 <1.txt



#### 8、^
取消特殊符号的作用

例子：
```bat
echo ^> >c:\1.txt
```

^是对特殊符号"<",">","&"的前导字符，
在命令中他将以上3个符号的特殊功能去掉，
仅仅只把他们当成符号而不使用他们的特殊意义。

比如
```bat
echo test ^>1.txt
```
结果则是
他没有追加在1.txt里，呵呵。只是显示了出来






#### 9、%
这个符号我们会在以后的教程中详细介绍到






#### 10、*
通配符号，表示任意个字符

例子：
```bat
del c:\windows\*.log
```








#### 11、?
通配符号，表示任意一个字符

例子：
```bat
dir c:\?indows
```





#### 12、.
表示当前目录

例子：
```bat
dir .\
```

(测试是可以，但是好像\和.好像没啥多用？)








#### 13、..
表示上一级目录

例子：
```bat
dir ..\
```





#### 14、" "
界定符号，通常用来引用有空格的目录

例子：
```bat
dir "c:\Documents and settings"
```

双引号允许在字符串中包含空格，进入一个特殊目录可以用如下方法

```bat
cd "program files"
cd progra~1
cd pro*
```


以上三种方法都可以进入program files这个目录





#### 15、:
标签定位符号，表示后面的内容是一个标签名

例子：
```bat
@echo off
:again
echo 欢迎来到新世纪网安基地学习!
pause
goto again
```





#### 16、,
某些时候可以当空格来使用

例子：
```bat
echo,
dir,c:\
```






#### 17、;
分号，当命令相同时，可以将不同目标用来隔离
但执行效果不变，如执行过程中发生错误，则只返回错误报告，但程序还是会执行。

例子：
```bat
dir c:\;d:\
```

例子：
```bat
dir z:\;d:\
```







#### 18、::
表示后面的语句是注释。相当于c++中的"//"

例子：
```bat
@echo off
::显示c盘根目录文件
dir c:\
pause
```


综合实例：
```bat
@echo off
ping /n 3 www.qq.com||shutdown /r /t 60 /c 命令执行失败了! && exit
%0
```


这条批处理文件主要是用ping命令来判断网络的连通性，当我们的ping命令执行成功后
就不会执行它后面的内容。那假如没有ping通的话就执行它后面的相关命令了。
%0它表示的就是无限循环的执行我们批处理程序。

