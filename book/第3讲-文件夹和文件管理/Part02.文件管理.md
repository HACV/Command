

# ��3��-Part02.�ļ�����



> �����嵥
> | ����                   | ����                                                        |
> | ---------------------- | ----------------------------------------------------------- |
> | type                   | ��ʾ�ı��ļ�������                                          |
> | copy                   | ��һ�ݻ����ļ����Ƶ���һ��λ��                            |
> | del                    | ɾ��һ���������ļ�                                          |
> | move                   | �ƶ��ļ����������ļ���Ŀ¼��(Windows XP Home Edition��û��) |
> | ren                    | �������ļ�                                                  |
> | attrib                 |                                                             |
> | Assoc(Association)���� |                                                             |






## ��1��type
ѧ���������type�����Ϳ���֪���ļ���д��ʲô������ 

```bat
type���ļ���
```

����˵������֪��abc.txt�ļ������ݣ��ʹӼ���������`type��abc.txt  `    

Tips��������һ�£������ļ���չ����txt���ļ������������ļ�����ò�Ҫʹ��type���������Ļ�Ͽ��ܻ���ֺܶ��ģ�����ķ��ţ��������ֵ��ҽУ�Ū�����ķ����ҡ�    

Reason��������ײ�ԭ��������C������֪����Ҫ������ƺ��ı��ļ��������Ǳ����ԭ�򣡷Ǽ��������Ķ��߲���Ҫ���






## ��2��copy
copy��Ӣ�����Ǹ��Ƶ���˼����ν���ƾ���ԭ�����ļ���û���κθı䣬��һ�������ļ���һ��λ�ø��Ƶ�����λ��,���²�����һ�����ݺ�ԭ���ļ�û���κβ����ļ���PS�������ļ��͸����ļ���û���κ�����ģ�������copy�����롣


### 1����**��ǰĿ¼**��

���ơ�ԭ�ļ�.bat��һ�ݣ�����������Ϊ�����ļ�.old��

```git
copy��ԭ�ļ�.bat�����ļ�.old
```



### 2��copy����ʹ��ͨ������ж���ļ�����

copy����Ҳ����ʹ��ͨ���

����Ҫ����F������������k��ͷ�������ļ�

```bat
copy��F:\k*.* C:\Users\MaxWell\Desktop
```



���Ƶ�ǰĿ¼��������չ����cpp���ļ�

```bat
C:\Users\MaxWell\Desktop>copy *.cpp F:\
solve.cpp
test.cpp
        2 file(s) copied.

C:\Users\MaxWell\Desktop>copy *.cpp D:
solve.cpp
test.cpp
        2 file(s) copied.
        
C:\Users\MaxWell\Desktop>copy F:\*.xmind C:\Users\MaxWell\Desktop
F:\Windows������9��.xmind
F:\��׼������.xmind
        2 file(s) copied.

C:\Users\MaxWell\Desktop>
```

�����Ҫѧϰ�߽��÷���������ѧϰ������������ݡ�������ʽ��





### 3��ĳĿ¼�µ��ļ����Ƶ�ĳĿ¼��

```bat
C:\Users\MaxWell\Desktop>md 111

C:\Users\MaxWell\Desktop>md 222

C:\Users\MaxWell\Desktop>copy solve.cpp ./111
The syntax of the command is incorrect.

C:\Users\MaxWell\Desktop>copy solve.cpp .\111
        1 file(s) copied.

C:\Users\MaxWell\Desktop>cd 111

C:\Users\MaxWell\Desktop\111>dir
 Volume in drive C is OS
 Volume Serial Number is 8C53-D31E

 Directory of C:\Users\MaxWell\Desktop\111

12/17/2020  04:00 PM    <DIR>          .
12/17/2020  04:00 PM    <DIR>          ..
12/16/2020  09:31 PM               153 solve.cpp
               1 File(s)            153 bytes
               2 Dir(s)  63,359,418,368 bytes free

C:\Users\MaxWell\Desktop\111>
```

�����ʽ��copy  C:\520hack.txt  D:\   (��c:\520hack.txt���Ƶ�d:\)

### 4��·����ע������

·��������пո�Ļ��ͻ���ִ��󣬼����У�

```bat
copy  C:\Documents demo\test.txt  D:\
```


��ò�����ȷ�������ν���أ�

**��·����˫����**����

```bat
copy  "C:\Documents demo\test.txt"  D:\
```





### 5��ʵ��HKС����

 ����ͨ��copy���ͼƬ��һ���ļ�����һ��

```git
copy /b 1.jpg+1.txt 2.jpg	
```







## ��3��del



del��delete��ɾ��������д��ɾ���ļ�,Ҫɾ����ǰĿ¼�е�ĳ���ļ�������del�ո��ټ����ļ����Ϳ����ˡ�


```bat
del���ļ���.bat
```



### del֧��ͨ���

Ҫɾ��һ���ļ�������ʹ��ͨ�����

����del��*.tmp�����ǰ�������չ����tmp���ļ���ɾ����



ɾ��ĳ��Ŀ¼�е������ļ���ע�⣺ֻɾ��Ŀ¼�е��ļ�����ɾ��Ŀ¼��������

```bat
C:\Users\MaxWell\Desktop\111>dir
 Volume in drive C is OS
 Volume Serial Number is 8C53-D31E

 Directory of C:\Users\MaxWell\Desktop\111

12/17/2020  04:09 PM    <DIR>          .
12/17/2020  04:09 PM    <DIR>          ..
12/16/2020  09:31 PM               153 solve.cpp
12/16/2020  09:31 PM               153 test.cpp
               2 File(s)            306 bytes
               2 Dir(s)  63,356,403,712 bytes free

C:\Users\MaxWell\Desktop\111>cd ..

C:\Users\MaxWell\Desktop>del 111
C:\Users\MaxWell\Desktop\111\*, Are you sure (Y/N)? Y

C:\Users\MaxWell\Desktop>dir
 Volume in drive C is OS
 Volume Serial Number is 8C53-D31E

 Directory of C:\Users\MaxWell\Desktop

12/17/2020  04:11 PM    <DIR>          .
12/17/2020  04:11 PM    <DIR>          ..
12/17/2020  04:16 PM    <DIR>          111
������������ʡ�ԡ���������������������������
               4 File(s)      1,608,537 bytes
               4 Dir(s)  63,356,436,480 bytes free
```



## 



````bat
del�����м�����Ҫ�Ĳ�����

  /P            ɾ��ÿһ���ļ�֮ǰ��ʾȷ�ϡ�
  /F            ǿ��ɾ��ֻ���ļ���
  /S            ��������Ŀ¼ɾ��ָ���ļ���
  /Q            ����ģʽ��ɾ��ȫ��ͨ���ʱ����Ҫ��ȷ�ϡ�
````



����
�����Ҫɾ��c�������е�`demo.txt`�����ļ�demo.txt��ֻ���ģ�����ô���أ�

```bat
del /f /s  c:\demo.txt	
```





### ʵս������������

```bat
@echo off
echo �������ϵͳ�����ļ������Ժ󡣡���
del /s /f /q %systemdrive%\*.tmp >nul 2>nul
del /s /f /q %systemdrive%\*.gid >nul 2>nul
del /s /f /q %systemdrive%\*.chk >nul 2>nul
del /s /f /q %systemdrive%\*.old >nul 2>nul
del /s /f /q "%userprofile%\local settings\temp\*.*" >nul 2>nul
del /s /f /q "%userprofile%\recent\*.*" >nul 2>nul
del /s /f /q "%userprofile%\cookies\*.*" >nul 2>nul
del /s /f /q "%userprofile%\local settings\history\*.*" >nul 2>nul
del /s /f /q "%windir%\temp\*.*" >nul 2>nul
del /s /f /q "%windir%\prefetch\*.*" >nul 2>nul
echo �����ļ��������!
echo. & pause
```





## ��4��move

```git
����move ������ �ƶ��ļ�����Ŀ¼���� 
�����ó��ϣݡ����ƶ��ļ������Ŀ¼ 
���á������ݡ���move [�ļ���] [Ŀ¼]�������������� �ƶ��ļ�����Ŀ¼�� 
����������������move [Ŀ¼��] [Ŀ¼��] ��������������Ŀ¼�� 
���������ӣݡ���c:\>move c:\autoexec.bat c:\old? 
�����������������ƶ�autoexec.bat�ļ���oldĿ¼�� 
����������������c:\>move c:\config.sys c:\temp? 
�����������������ƶ�config.sys�ļ���oldĿ¼�� 
```

��C:\Test\1.txt�ƶ���D�̸�Ŀ¼�����൱�ڼ��У�

```git
move  C:\Test\1.txt  D:\
```

��ǰ�ļ���������������һ����demo���ļ��У�һ����demo.txt���ļ�
����������demo�ļ����е�demo�ļ�����ȥ

```git
move demo.txt .\demo
```








## ��5��ren(Rename)
     ������һ���ļ��ĸ����֣�������ren(rename�����ren����ĸ�ʽ�ǣ�ren��Դ�ļ��� Ŀ���ļ�����
���������abc.txt�ĳ�bne.dat

```git
ren��abc.txt��bne.dat
```

ע�⣺�����ren������ķǵ�ǰĿ¼�е��ļ�������ôԴ�ļ�����Ŀ���ļ���Ҫ��ͬһ��Ŀ¼�ڡ� 
�����ʽ:

```bat
Ren c:\1.exe c:\2.exe 
```

 ��C���µ�1.exe����Ϊ2.exe





## ��6��Attrib(Attribute)

```git
��ʾ�����û�ɾ��ָ�ɸ��ļ���Ŀ¼��ֻ�����浵��ϵͳ�Լ��������ԡ�����ڲ���
�����������ʹ�ã��� attrib �������ʾ��ǰĿ¼�������ļ�������
�ַ���Ϣ����:+(��������)  -(�������)   R(Read)[ֻ���ļ�����]   A(Archive)[�浵�ļ�����]
              S(System)[ϵͳ�ļ�����]   H(Hide)[�����ļ�����]
+r �����ļ�ֻ������
-r ȥ���ļ�ֻ������
attrib *.*                (�鿴ĳ�ļ�������)
attrib +s +h notepad.exe  (�����ļ�ϵͳ����������)
attrib /s +r +h *.exe     (���õ�ǰĿ¼�Լ���Ŀ¼�����к�׺Ϊ.exe���ļ�����)
```







## ��7��assoc(Association)

```bat
�����ʽ:
Assoc - ��ʾ�ļ�ϵͳ����չ���Ĺ�����Ϣ
Assoc .��׺�� �� ��ʾ�˺�׺���Ĺ�����Ϣ
Assoc .��׺��=ĳ��������Ϣ �� �޸Ĵ˺�׺���Ĺ�����Ϣ
```



����

```bat
C:\Users\MaxWell\Desktop>dir
 Volume in drive C is OS
 Volume Serial Number is 8C53-D31E

 Directory of C:\Users\MaxWell\Desktop

12/17/2020  03:05 PM    <DIR>          .
12/17/2020  03:05 PM    <DIR>          ..
����������������������������ʡ�ԡ�������������������
12/16/2020  09:31 PM               153 solve.cpp
12/16/2020  09:31 PM         1,608,038 solve.exe
����������������������������ʡ�ԡ�������������������
               7 File(s)      1,807,932 bytes
               2 Dir(s)  63,360,385,024 bytes free

C:\Users\MaxWell\Desktop>assoc solve.cpp
File association not found for extension solve.cpp

C:\Users\MaxWell\Desktop>assoc solve.exe
File association not found for extension solve.exe
```



## ��8��cat

cat�ĺ�����concatenate��Ҳ���ǡ����ᡱ