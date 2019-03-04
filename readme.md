# 此版本不是最终版本

# 实验目的

1. 认识linux 中的权限问题,理解用户和用户组
2. 认识unix 中的文本，理解UNIX 为什么要使用文本
3. 认识linux 中的文件，学习你的linux系统中文件的基本情况，认识到linux中任何东西都是文件

4. 学习和使用管道指令、重定位指令；
5. 进程查看以及创建链接文件的方法；
6. 了解make指令的使用方法；

# 实验指导
写在最前面:原老师提供了一份其他UNIX环境编程的课件，讲解十分详细，可供大家参考，写在实验指导中的内容毕竟没有经过若干时间的打磨，有些粗糙在所难免，欢迎大家指出问题，同时极力推荐大家多阅读其他的内容，我们会提供一个比较优质的资源。
一些可供选择的资源：
http://billie66.github.io/TLCL/book/  （不知道什么原因非常不稳定，有时候无法访问）


经过上一次实验，同学应该已经掌握了基本的linux下的命令和工具。
linux系统的使用，还希望大家不止在实验课上使用，只有使用可以巩固自己的记忆。 

## 认识权限 

当你使用`ls -l`命令的时候, 会发现列出了目录的很多信息，并且以行为单位，下来就认识一下这些文件的基本含义
首先 -l 选项代表ls (- long) 就是展示目录下的详细信息。 比如如下例子
[me@linuxbox ~]$ ls -l
total 56
drwxrwxr-x 2  me  me  4096  2007-10-26  17:20  Desktop
drwxrwxr-x 2  me  me  4096  2007-10-26  17:20  Documents
drwxrwxr-x 2  me  me  4096  2007-10-26  17:20  Music
drwxrwxr-x 2  me  me  4096  2007-10-26  17:20  Pictures
drwxrwxr-x 2  me  me  4096  2007-10-26  17:20  Public
drwxrwxr-x 2  me  me  4096  2007-10-26  17:20  Templates

1. 第一个字段是这个文件的权限,第一个d表示这是一个目录，其余九个字段表示这个文件的详细权限，一个rwx为一组 表示一个读(r) 写(w) 执行(x) 的权限，总共有三组，分别代表了拥有者，拥有组，所有人 对这个文件的权限，对应的字段为-表示没有该权限
   ​		“-”表示普通文件；

   ​		“d”表示目录；

   ​		“l”表示链接文件；

   ​		“p”表示管理文件；

   ​		“b”表示块设备文件；

   ​		“c”表示设备文件；

   ​		“s”表示套接字文件；

   ​	2）文件属性，其属性可分为三段：\[rwx]\[rwx][r-x]，其中：

   ​		**r**（Read，读取权限）：对文件而言，具有读取文件内容的权限；对目录来说，具有浏览目录的权限；

   ​		**w**（Write，写入权限）：对文件而言，具有新增、修改文件内容的权限；对目录来说，具有删除、移动目录内文件的权限；

   ​		**x**（eXecute，执行权限）：对文件而言，具有执行文件的权限；对目录来说，该用户具有进入目录的权限。

2. 第二个字段表示该文件硬连接的数目，这个问题以后再说
3. 第三个&第四个字段 分别表示所有人和所有组，这里表示拥有人和拥有组都是me 
4. 第五个字段表示以字节数表示的文件大小。
5. 最后修改时间
6. 文件名
+ 用户及用户组
Linux用户分为管理员和普通用户，普通用户又分为系统用户和自定义用户。可以查看/etc/passwd来查看；
   ​	1）系统管理员：即root帐户，拥有所有系统权限，是整个系统的所有者。
   ​	2）系统用户：linux为满足自身系统管理所内建的账号，通常在安装过程中自动创建，不能用于登录操作系统。
   ​	3）自定义用户：由root管理员创建供用户登录系统进行操作使用的账号。
   ​	在linux中的每个用户必须属于一个组，不能独立于组外。在linux中每个文件有所有者、所在组、其它组的概念。同样用户组的信息我们可以在/etc/group中查看。
​+用户管理命令（详情请使用`man`指令）
         添加用户命令：useradd
​			修改用户密码：passwd
​			修改用户信息：usermod
​			修改用户密码状态：chage
​			删除用户命令：userdel
​			查看用户：id
​			切换用户身份：su
​			修改用户组：groupmod
​			添加用户组：groupadd
​			删除用户组：groupdel
## 认识文件
`file` 命令可以帮助你认识文件，file <文件名> 会输出这个文件的类型 

## 关于文本

### 开机启动脚本 

### shell脚本

### shell启动脚本

### make 


关于unix 下为什么使用文本《UNIX编程艺术》第5章中给了详细的说明，相信通过长时间的使用，你也能感受到其中的优越之处
这里仅仅给出两个截图，感兴趣的同学可以自行查阅（这本书很有趣的）
![例子1](https://github.com/sfzyk/system-programming-ta/blob/master/example1.png)
![例子2](https://github.com/sfzyk/system-programming-ta/blob/master/example2.png)
![重点](https://github.com/sfzyk/system-programming-ta/blob/master/example3.png)

#实验任务


#提交方式

将自己的答案放在word文件里，标清题号，不用复制题目和前面的实验指导。以.docx或.doc的文件格式提交至软件学院云平台，以便于助教批改。请不要抄袭他人，被查重者将严肃处理。

命名规则：学号\_姓名\_实验二

截止提交时间：
如有错误或不当的地方，欢迎大家指出