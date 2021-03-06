# Ubantu.Linux基本命令

## 一. 对目录的操作
1. ### cd 

进入目录

**用法**
```c
cd [目录]
```

.代表当前目录，..代表上一层目录，如果目录名字太长可以先输入目录名的前几个字母再按TAB键补完。

使用时cd .. ，如果不加参数，就会回到家目录。

你可以一次创建很多目录，用空格相隔开。注意，如果要创建带空格的目录，需要用引号或者\符号

2. ### mkdir
创建目录

**用法**

```c
mkdir [参数] [目录名]
```
参数：

-p 可以通过这个命令建立一个很深的子目录，它会自动创建父目录。


3. ### rmdir

**只能删除空目录**

用法同 mkdir

如果要删除一个有内容的目录，用 rm -r [目录名] 这条命令，会连同目录下的子目录都会删去。



4. ### pwd

显示当前所在的目录


**用法**

```c
pwd
```

5. ### 目录的拷贝

```c
cp -a [目录名] [目录名]
```

## 二. 文件的管理

1. ### ls

**用法**

```c
ls [文件名]    // 列举目录和文件
ls -a         // 列举文件，目录及隐藏文件，即是以 . 开头的文件
ls -l         // 列举文件的权限，大小等详细信息
ls -R         // 递归列举一个目录下的所有子目录中的文件
ls -X         // 以文件扩展名排列，便于找出同一类文件
```


2. ### cat

输出一个文件（查看文件内容）

**用法**
```c
cat [参数] [文件名]
```
参数：

  -b  只对非空行显示行号
  -E  在每一行结束时显示$字符
  -n  对所有行显示行号
  
  
提示

可以一次输入很多文件名字，用空格隔开。






3. ### mv

移动一个文件，也可以进行重命名


**用法**
```c
mv [参数] [源文件] [目的位置+文件名]
  如果不给目的文件名，则默认不改名。
```

参数:

  -b 如果目的文件存在，那么就创造一个备份
  -f 强行移动，在目的文件存在的时候覆盖这个文件。默认选项
  
  
  
  
4. ### cp
复制


5. ### rm
删除文件



1. 对文件进行压缩和解压 

```c
gzip filename      //压缩
gunzip filename    //解压
```
或

```c
bzip2 filename
bunzip2 filename
```
2. 对文件和目录压缩和解压

```c
tar czvf file.tar.gz(压缩包的名字)  dir(要压缩的目录名)   // czvf 中c-->create, z-->压缩包类型gzip  可以使用man tar命令查看具体用法,v可以省                      略  
tar cjvf file.tar.bz2 dir   
tar cJvf file.tar.xz dir
tar xvf file.bar.gz(xz)  // 解压，以上三种类型都可解压
```


## Linux下常见的两种软件包管理机制

* RPM  (红旗版本下)
* Deb (Ubantu版本下)  常用命令dpkg, apt。

### 关于Deb软件包机制的讲解

#### Deb软件包名称的组成

**比如: sl_3.03-17_amd64.deb**
```c
sl, 表示软件包名称
3.03-17, 表示版本号和修订版本号
amd64, 表示运行机器的平台架构
deb, 表示deb软件包的后缀名
```



1. 本地安装包管理
* 软件包安装 dpkg -i sl_3.03-17_amd64.deb
* 软件包卸载  dpkg -r sl
* 软件包彻底卸载，移除所有配置文件 dpkg -P sl
* 查看软件包的安装状态 dpkg -s sl
* 查看软件包的安装路径 dpkg -L sl
* 列出所有安装的软件包 dpkg -get-selections

2. 在线管理操作命令

* 在软件包安装前，先要更新一下本地软件源  apt-get update 
* 软件包安装 apt-get install sl
* 软件包的卸载 apt-get remove sl
* 彻底卸载 apt-get remove --purge sl

关于update 和 upgrade
目的是update是下载源里面的metadata的. 包括这个源有什么包, 每个包什么版本之类的.## 文件的归档和压缩安装软件之前, 可以不upgrade, 但是要update. 因  为旧的信息指向了旧版本的包, 但是源的服务器更新了之后旧的包可能被新的替代了, 于是你会遇到404...

[update](https://www.zhihu.com/question/21732981)




## openssh 

openssh是ssh协议的免费开源实现。SSH协议族可以用来远程控制，或在计算机之间传送文件。

安装openssh-server和openssh-client

安装完后

通过 
```c
ssh 用户名@ip地址
```

远程控制计算机

通过

```c
scp 用户名@ip地址:某个目录下的文件名/目录名     // 目录名要在scp后加-r
```

来拷贝远程系统的文件或目录

给远程系统传文件是以下命令

```c
scp filename(要传的文件) 用户名@ip地址:/dir/filename1 (重命名为filename1)
```

