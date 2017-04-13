# notebook


[html参考文献](http://www.w3school.com.cn/html/html_intro.asp)

[bootstrap](http://www.runoob.com/bootstrap/bootstrap-tutorial.html)


# HTML
## html常用标签及属性
**标签分类：**
1. 块元素

独占一行或几行，具有宽，高，对齐等属性
```html
<h1>~<h6>,<p>,<div>,<ul>,<ol>,<li>
```
等

2. 行内元素

一般的行内元素不具有宽，高，对齐等属性
```html
<img />,<a>,<span>
```
及文本格式标签等

3. 特殊行内元素

例如： <img />、 <input /> 、<td>，可以设置宽高和对齐


### 常用标签

标签名| 格式
-----|------|
段落 | p
标题 | h1~h6
水平线| hr
换行  | br
加粗  |strong/b
倾斜  | i/em
删除线 |del/s
下划线 | u/ins

### 图像标签
```html
<img src="路径" title="标题" alt="图片不正常显示时的文本提示">
```
### 超链接标签

```html
<a href="/resource/k111/前端基础知识/class-002/跳转目标" target="窗口弹出方式">文本或者图像</a>
```
href：用于指定链接目标的url地址，当为<a>标记应用href属性时，它就具有了超链接的功能。
target：用于指定链接页面的打开方式，其取值有_self和_blank两种，其中_self为默认值，_blank为在新窗口中打开方式

### 锚点链接
通过创建锚点链接，用户能够快速定位到目标内容。

即可以跳转本页面的某一部分内容，也可跳转到其他页面的某一特定位置

创建锚点链接分为两步：

* 使用“链接文本”创建链接文本。
* 使用相应的id名标注跳转目标的位置
```html
<a href="#hdl"></a>
<h1 id="hdl"> 1242<h1>
```

### 列表

#### 无序列表
```html
<ul>
  <li>列表项一</li>
  <li>列表项二</li>
  <li>列表项三</li>
</ul>
```
li 可以容纳所有元素，ul 中只能嵌套li
#### 有序列表

```html
<ol>
  <li>列表项一</li>
  <li>列表项二</li>
  <li>列表项三</li>
</ol>
```
ol 可以定义 start属性，li 可定义value属性
#### 定义列表
```html
<dl>
    <dt>名词1</dt>
    <dd>名词1解释1</dd>
    <dd>名词1解释2</dd>

    <dt>名词2</dt>
    <dd>名词2解释1</dd>
    <dd>名词2解释2</dd>
</dl>
```
### 表格


td标签属性

属性名  |  含义  |  常用属性值
-------|--------|-----------
rowspan | 纵向合并单元格(行)| 像素值
colspan | 横向合并单元格(列) | 像素值

## CSS

### css选择器
* 标签选择器
* 类选择器
* id选择器
* 通配选择器
* 后代选择器
* 交集选择器
* 并集选择器

```html
<!DOCTYPE>
<html>
  <head>
    <meta charset="utf8"/>
    <title>CSS</title>
    <style>
    /* 通配选择器，能匹配页面中所有的元素，当一个页面中有多个选择器且选择器里的属性名和通配选择器的
    里的属性名一样时，就选择其他选择器*/
    * {
      background:pink;
      font-size:50px;
    }
    /* 标签选择器，将页面中的同类型的标签统一样式，不利于差异设计*/
      h3{
         color:blue;
         font-size:30px;
       }
       /* 类选择器可以为元素定义单独样式，也可以相同样式*/
       .red{
         color:red;
       }
       /* id选择器，html元素的id是唯一的，使用id选择器只对应某个元素*/
       #fonts{
         font-size:40px;
         color:orange;
       }   


    </style>
  </head>
  <body>
    <h3>hello world</h3>
    <h3 class="red">hello world</h3>
    <h3 class="red">hello world</h3>
    <p id="fonts">这是一段话</p>
  </body>
  </html>
```

```html
<!DOCTYPE>
<html>
  <head>
    <meta charset="utf8"/>
    <title>css样式</title>
    <style>
    /* 后代选择器 div里的p标签*/
       div p{
         color:pink;
         font-size:80px;
       }
       div p span{
         color:orange;
       }
       /* 交集选择器 在一个块内出现多个同名标签时，需要设置某一个标签时*/
       div p.cll{
         font-size:50px;
       }
       /* 并集选择器 将多个不同类型的标签合在一起设置*/
       h4, h6{
         color:blue;
       }
    </style>
  </head>
  <body>
    <div>
      <p>jfsdklgjdsklgjdslk</p>
      <div>
     <p>123456<span>hhhhhh</span></p>
   </div>
   </div>
  <div>
     <p class="cll"> niaho</p>
     <p> hihihi</p>
     <p> hello</p>
  </div>
  <div>
     <h4> 哈哈哈哈</h4>
     <h6> 号楼打开</h6>
     <span> 哈佛斯塔克</span>
  </div>
  </body>
</html>
```

