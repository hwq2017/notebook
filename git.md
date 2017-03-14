# git
1. 什么是git？
* GIT 是一个**分布式版本控制软件**
* 分布式版本控制系统根本没有“中央服务器”，每个人的电脑上都是一个完整的版本库，这样，你工作的时候，就不需要联网了，因为版本库就在你自己的电脑上。既然每个人电脑上都有一个完整的版本库，那多个人如何协作呢？比方说你在自己电脑上改了文件A，你的同事也在他的电脑上改了文件A，这时，你们俩之间只需把各自的修改推送给对方，就可以互相看到对方的修改了。

# git安装
### ubantu linux 安装方法：
```sh
$ sudo apt-get install git
```
### Mac ox 安装方法：
1. 下载安装 xcode 开发工具里的 xcode-commnadline 本身带git管理工具.
1. 使用brew安装工具直接安装
```sh
$ brew install git
```

# 创建git本地仓库
### 获取git仓库
1. **在现有的目录里初始化仓库**
2. **克隆现有仓库**

什么是版本库？
* 版本库又名**仓库**，英文名repository，你可以简单理解成一个目录，这个目录里面的所有文件都可以被**Git**管理起来，每个文件的修改、删除，**Git**都能跟踪，以便任何时刻都可以追踪历史，或者在将来某个时刻可以“还原”。
1. 先要创建一个目录，用来存放仓库。
```sh 
$ mkdir huangwenqian
$ cd huangwenqian
```
2. 使用git init命令，将当前目录创建成git仓库
```sh
$ git init (初始化一个空的仓库)
```

# 增加文件
1. 复制已有的文件到当前目录里：
```sh
$ cp ../../huangwenqian2/*.c .
```
2. 创建一个新的文件
```sh
$ touch hello.c
$ vi hello.c
```

# 查看目录状态
查看当前目录下的文件在git仓库里的状态
```sh
$ git status
```

# 跟踪文件
将当前目录下的**所有文件**进行跟踪（将目录里的所有文件添加到仓库里）
```sh
$ git add .
```
```sh
$ git add filename //将一个文件进行跟踪
```

# 配置个人用户信息
当安装完 Git 应该做的第一件事就是设置你的用户名称与邮件地址。 这样做很重要，因为每一个 Git 的提交都会使用这些信息，并且它会写入到你的每一次提交中，不可更改：
```sh
$ git config --global user.name "Emaliy.huang"
$ git config --global user.email "wenqian.h@outlook.com"
```
再次强调，如果使用了 **--global** 选项，那么该命令只需要运行一次，因为之后无论你在该系统上做任何事情， Git 都会使用那些信息。 当你想针对特定项目使用不同的用户名称与邮件地址时，可以在那个项目目录下运行没有 --global 选项的命令来配置。

# 配置文本编辑器
既然用户信息已经设置完毕，你可以配置默认文本编辑器了，当 Git 需要你输入信息时会调用它。 如果未配置，Git 会使用操作系统默认的文本编辑器，通常是 Vim。 如果你想使用不同的文本编辑器，例如 Emacs，可以这样做：
```sh
$ git config --global core.editor emacs
```

# 提交
向本地git仓库提交跟踪文件
```sh
$ git commit
```

# 查看提交信息
查看提交相关信息
```sh
$ git log
```
结果：
```sh
第一行：commit ID
第二行：提交作者名字和email
第三行：提交时间
第四行：提交信息标题
第五行：提交信息具体内容
```

# 删除文件
1. 删除文件后，恢复文件。
```sh
$ rm -rf hello.c
$ git status
$ git checkout hello.c
```
2. 从版本库里删除文件。（真正删除文件）
```sh
$ git rm hello.c (or) rm hello.c
$ git status
$ git add .
$ git commit
```

# 版本之间的比较
1. 查看修改源码（未修改的与修改后的进行比较，这是在修改后的文件还没被提交的基础上进行比较）
```sh
$ git diff
```
2. 两个提交版本之间的比较
```sh
$ git diff commitID-1 commitID-2
```

# 版本之间的切换
根据commitID，可以进行版本切换
```sh
$ git reset --hard commitID
```

# 忽略文件
忽略不需要跟踪到git仓库里的文件
```sh
$ touch .gitignore
$ vim .gitignore     //将a.out 文件写到 .gitignore文件里进行忽略掉
------
a.out      
------
$ git add .
$ git commit
```


# 什么是patch
patch多指补丁的意思, 在这里更多的指程序有一些bug, 需要我们进行fixed, 那fixed源码文件就是patch.

patch实际上是保存两个文件的差异.

# git生成patch
```sh
$ git format-patch -p1
```

# github
1. 注册github帐号

   1. 注册邮箱，注意不要使用QQ.com
   
2. 创建一个仓库，例如notebook仓库

3. 从github将创建的notebook仓库,克隆到本地
```sh
$ git clone http://github.com/hwq2017/notebook.git  
```
4. 将本地仓库与github仓库进行同步，并将本地提交推送到服务器上
```sh
$ git push origin master
input username:
input password:
```
5. 更新本地仓库，与github仓库进行同步。将服务器的提交拉取到本地
```sh 
$ git pull
```
