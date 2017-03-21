# 安装apache web服务器
安装步骤:

```sh
$ sudo apt-get update
```

### tasksel

用tasksel可以方便安装dns server,lamp, kubuntu desktop, ubuntu desktop, xubuntu之类的软件包。
这个软件在server版是预装的，而在桌面版里是不预装的，想用的话需先安装：
```sh
$ sudo apt-get install tasksel
```
使用这个软件的话就用下面命令：
```sh
$ sudo tasksel
```
选择LAMP server选项， 安装过程中需要设置mysql数据的root密码， 统一设置为123456。

重启Apache服务器
```sh
$ sudo /etc/init.d/apache2 restart
```





# CGI（通用网关接口）
**CGI**(Common Gateway Interface) 是WWW技术中最重要的技术之一，有着不可替代的重要地位。CGI是外部应用程序（CGI程序）与WEB服务器之间的接口标准，是在CGI程序和Web服务器之间传递信息的过程。CGI规范允许Web服务器执行外部程序，并将它们的输出发送给Web浏览器，CGI将Web的一组简单的静态超媒体文档变成一个完整的新的交互式媒体。

Common Gateway Interface，简称CGI。在物理上是一段程序，运行在服务器上，提供同客户端HTML页面的接口。这样说大概还不好理解。那么我们看一个实际例子：现在的个人主页上大部分都有一个留言本。留言本的工作是这样的：先由用户在客户端输入一些信息，如评论之类的东西。接着用户按一下“发布或提交”（到目前为止工作都在客户端），浏览器把这些信息传送到服务器的CGI目录下特定的CGI程序中，于是CGI程序在服务器上按照预定的方法进行处理。在本例中就是把用户提交的信息存入指定的文件中。然后CGI程序给客户端发送一个信息，表示请求的任务已经结束。此时用户在浏览器里将看到“留言结束”的字样。整个过程结束。

### 处理步骤

1. 通过Internet把用户请求送到web服务器。

1. web服务器接收用户请求并交给CGI程序处理。

1. CGI程序把处理结果传送给web服务器。

1. web服务器把结果送回到用户。

## 配置CGI的步骤
```sh
1. $ sudo ln -s /etc/apache2/mods-available/cgi.load /etc/apache2/mods-enabled/cgi.load
```
2. 重启apache服务器
```sh
$ sudo service apache2 restart
```
3. 需要运行的cgi文件的存放路径为 /usr/lib/cgi-bin



# 安装Atom
1. 打开浏览器，在地址栏中输入：[https://atom.io](https://atom.io/)下载安装包。
2. 使用dpkg进行安装。
```sh
$ sudo dpkg -i atom-64.deb
```
3. 需要安装的第三方库
* activate-power-mode：动感插件 atl + ctrl + o :打开插件

* vim-mode：vim模式

* ex-mode：实现:w功能
 


