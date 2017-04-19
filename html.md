# notebook


[html参考文献](http://www.w3school.com.cn/html/html_intro.asp)

[bootstrap](http://www.runoob.com/bootstrap/bootstrap-tutorial.html)


# HTML
```html
<!DOCTYPE>   ---->文档类型声明
<html></html> ---->整个文档页面
<meta/>      ---->设置页面编码格式，关键字，以及页面的描述
<title></title> --------->标题部分
<head></head>   ------>页面的头部分
<body></body>   ------>页面的主体部分


```




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


<ul>
  <li>列表项一</li>
  <li>列表项二</li>
  <li>列表项三</li>
</ul>

li 可以容纳所有元素，ul 中只能嵌套li



#### 有序列表

```html
<ol>
  <li>列表项一</li>
  <li>列表项二</li>
  <li>列表项三</li>
</ol>
```


<ol>
  <li>列表项一</li>
  <li>列表项二</li>
  <li>列表项三</li>
</ol>



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


<dl>
    <dt>名词1</dt>
    <dd>名词1解释1</dd>
    <dd>名词1解释2</dd>
    <dt>名词2</dt>
    <dd>名词2解释1</dd>
    <dd>名词2解释2</dd>
</dl>



### 表格

```html
<table>
    <tr>
    <td>单元格内的文字</td>
        ...
    </tr>
    ...
</table>
```
```md
在上面的语法中包含三对HTML标记，分别为<table></table>、<tr></tr>、<td></td>，他们是创建表格的基本标记，缺一不可，下面对他们进行具体地解释。
<table></table>：用于定义一个表格。
<tr></tr>：用于定义表格中的一行，必须嵌套在<table></table>标记中，在<table></table>中包含几对<tr></tr>，就有几行表格。
<td></td>：用于定义表格中的单元格，必须嵌套在<tr></tr>标记中，一对<tr></tr>中包含几对<td></td>，就表示该行中有多少列（或多少个单元格）。

注意：
学习表格的核心是学习<td></td>标记，他就像一个容器，可以容纳所有的元素
```
```md
在使用表格进行布局时，可以将表格划分为头部、主体和页脚，具体 如下所示：
<thead></thead>：用于定义表格的头部，必须位于<table></table>标记中，一般包含网页的logo和导航等头部信息。
<tfoot></ tfoot >：用于定义表格的页脚，位于<table></table>标记中<thead></thead>标记之后，一般包含网页底部的企业信息等。
<tbody></tbody>：用于定义表格的主体，位于<table></table>标记中<tfoot></ tfoot >标记之后，一般包含网页中除头部和底部之外的其他内容。
可以查看比如股票大盘等网站。
```
**table标签属性**

border
cellspacing
cellpadding
height
width
align
**caption**
紧随table之后，为表格定义标题

**th标签**
表头一般位于表格的第一行或第一列，其文本加粗居中

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
* 伪类选择器

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
       .one{
         font-size:40px;
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
    <h3 class="red one">hello world</h3> <!--这个h3 字体大小为40px，红色 -->
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


**伪类选择器**

Link:标签原本样式（如果在这个属性中设置样式优先级要高于标签选择器）
Visited:标签被访问以后的样式。
Hover:鼠标悬停在标签上会触发的样式。
Active:当点击（激活）标签时的样式。


```html
<!DOCTYPE>
<html>
<head>
  <meta charset="UTF-8">
  <title>伪类选择器</title>
     <style>
/* 访问顺序 l，v，h，a*/

     /* 默认的颜色*/
      div, .two:link{
         color:red;
       }
       /* 访问后的*/
       .two:visited{
         color:blue;
       }
       /* 鼠标放上去的颜色*/
       .two:hover{
         color:pink;
       }
       /* 点击时*/
       .two:active{
         color:orange;
       }
       /* 非链接标签 一般只用l，h*/
     </style>
</head>
<body>
  <a href="#"> 原始的a标签</a>
  <a class="two" href="#"> 使用伪类选择器设置的a标签</a>
  <div>kdkdfjskfj</div>
</body>
</html>

```
### css三种样式类型

**行内样式**

```html
<p stlyle="color:red;">这是css行内样式</p>
```

**嵌套样式**

写在head中，并且用style标签包含。

```html
<html>
<head>
<style>
p, a {
    color:red;
}
</style>   
</head>
<body>
<div>
  <p>p标签</p>
  <a href="/resource/k111/前端基础知识/class-003/#">a标签</a>
</div>
</body>
</html>
```

**外部样式**

将CSS编写为单独的文件，需要在head中引入。

```html
<head>
<link rel="stylesheet" href="CSS文件路径" type="text/css">   <!-- rel 指定当前文档与被链接文档的关系 stylesheet就是样式引用-->
</head>
```
 ### css的三大特性
 
 **继承**
 
 就是页面中的一些标签的属性可以继承给子标签,但是继承还是限制的,比如a的颜色，块级元素的高度等等。
一般情况下，所有的与文字图片的大小样式相当的属性都可以继承:font-x,line-x,一些标签的宽高也可以继承。
 
 ```html
 <html>
  <head>
  <meta charset="utf8">
  <title>css三大特性之 继承</title>
  <style>
  /* 页面中一些标签的属性可以继承给子标签，但是有些是由限制的，例如：a 的颜色，块级元素的高度等
   */
  div {
     font-size:50px;
     color:purple;
     height:200px;
  }
  </style>
  </head>
  <body>
    <h1>nihao shijie</h1>
    <div>
      <p>你好<span>北京</span></p>
      <a href="#">HHHH</a>
       <!-- h 标签的字体大小 = 当前设置的字体大小 * 对应的比例 (h 标签的对应比例为2em) 
          1em = 当前设置的字体大小的像素值px-->
       <h1>hello world</h1>
    </div>
  </body>
</html>
 ```
 
 **层叠**
 
页面的样式是多项属性设置进行叠加的结果

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>css三大特性之 层叠</title>
  <style>
  /* 层叠样式 就是多项不同属性设置进行叠加*/
    div p{
      color:green;
    }
    .p1{
      font-size:50px;
    }
  </style>
</head>
<body>
  <div>
    <p class="p1">好大家可控硅看大家发牢骚</p>
    <p>dfhskjflsdkfs;ldf</p>
  </div>
</body>
</html>
```
 
 **优先级**

当设置发生冲突时，需要考虑优先级，优先级最高的设置有效。

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>css三大特性之 优先级</title>
  <style>
/* 设置同一标签时：需要考虑优先级
 优先级的基本公式： style(行内) > id > class >标签 > 继承 > 浏览器的默认属性
  style > #pp >.p2 >.p1 > p > div > 默认*/

  p {
    font-size:50px;
    color:red;
  }
  div {
    color:blue;
  }
  /* 类选择器的优先级根据 其在style中的先后顺序*/
  .p1{
    color:green;
  }
  .p2{
    color:purple;
  }
  #pp{
    color:pink;
  }
  </style>
</head>
<body>
<div>
  <p style="color:orange" id="pp" class="p1 p2">春眠不觉晓</p>
</div>
</body>
</html>
```
```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>优先级</title>
  <style>
/* 出现一个标签，优先级值 = 1
  出现一个class，优先级值 = 10
  出现一个id ，优先级值 = 100*/

  p {
    color:red;  /* 优先级值是 1 */
  }
  div p{
    color:blue;  /*优先级值是 2 */
  }
  .p1{
    color:green;/*优先级值是 10 */
  }
  div .p2{
    color:pink; /*优先级值是 11*/
  }
  #pt{
    color:yellow;  /*优先级值是 100*/
  }
  </style>
</head>
<body>
  <div>
    <p class="p2">ABCDEFG HIJKLMN OPQRST UVWXYZ</p>
  </div>
</body>
</html>
```


### css样式属性

#### font字体属性

* font-size:字体大小
* font-family:字体类型
* font-weight:字体粗细
* font-style:字体风格，斜体，或正常
* font综合设置：
```html
选择器 {
  font: font-style font-weight font-size/line-height font-family;
}
```

顺序不能变，必须保留字体大小和类型

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>字体</title>
  <style>
     p{
       font-size:30px;       /*定义字体的大小 一般采用像素为单位*/
       font-family:"楷体","宋体";   /*设置字体类型：宋体等 。可以同时指定多个字体*/
     }
     .p1{
       font-weight:lighter;    /* 定义字体的粗细：normal，加粗（bolder或 数值100-900（100的整数倍）），正常 lighter*/
       font-style:italic;     /* 定义字体风格：斜体italic，倾斜oblique，正常字体normal*/
     }
     div{
       font:bolder italic 50px "宋体"; /*font属性综合设置，必须按照font-style font-weight font-size font-family
       这种语法格式书写，前两个值可以省略，但必须保存后两个值 */
     }
  </style>
</head>
<body>
  <span>的积分离开过将</span>
  <p class="p1">结果看来设定激发了开设的会计否</p>
    <P>几十块关键时刻的积分散开来</P>
    <div>gklsdsjfskldflsdjf</div>
</body>
</html>
```

#### 文本外观属性
**文本颜色color**

color属性用于定义文本的颜色，其取值方式有如下3种：
1. 预定义的颜色值，如red，green，blue等。
2. 十六进制，如#FF0000，#FF6600，#29D794等。实际工作中，十六进制是最常用的定义颜色的方式。
3. RGB代码，如红色可以表示为rgb(255,0,0)或rgb(100%,0%,0%)。

需要注意的是，如果使用RGB代码的百分比颜色值，取值为0时也不能省略百分号，必须写为0%。


**字符间距letter-spacing**

**单词间距word-spacing**

**行间距line-height: 行高**

用于设置字体的最顶端距离最低端的距离

设置方式：

1. 使用百分比,那么这个行高的基数为当前标签字体大小。
```md
line-height: 120%; 表示行高为当前字体的1.2倍,子元素会继承父元素计算出的行高
```
2. 直接使用px进行绝对设置
```md
line-height: 30px; 直接设置行高为30px
```
3. 使用em进行相对设置
```md
line-height: 1.5em; 设置行高为当前字体大小的1.5倍,子元素会继承父元素计算出的行高
```
4. 使用不带单位的数值
```md
line-height: 1.5; 设置行高因子为1.5,子元素会继承该因子而不是继承父元素行高
```
```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>行高</title>
  <style>
  div{
    font-size:40px;
  /*  line-height: 30px;  */     /* 设置字体的最顶段到最低段的距离,可直接使用px进行直接设置行高，但不要小于字体大小*/
    line-height: 120%; /*表示行高为当前字体大小的1.2倍，子元素会继承父元素计算出的行高 48*/
    line-height: 1.5em; /*表示行高为当前字体大小的1.5倍，子元素会继承父元素计算出的行高 */
    line-height: 1.2;  /* 子元素会继承该因子，而不是继承父元素计算出的行高*/
    /* 当多个同名属性出现在一个选择器中时，后面的会将前面的属性设置覆盖*/
  }
  div p{
    font-size: 30px;
  }
  </style>
</head>
<body>
  <div>
    <p>权威机构发刊该看否<br>
    价格还是饥渴的</p>
  </div>
</body>
</html>
```


**文本装饰text-decoration**

**水平对齐方式text-align**

**垂直对齐方式vertical-align**

**首行缩进text-indent**

```html
<html>
<head>
  <meta charset="UTF-8">
  <title>文本外观</title>
  <style>
  div{
    font-size: 30px;
    /* color 属性取值的三种方式 */
    /*color:orange;*/
    color:#ffbbaa;   /*最常用是 采用十六进制设置颜色 */
    /*color:rgb(120, 12, 34);  /*三原色红绿蓝的取值范围是0-255*/*/
  }
  .one{
    letter-spacing: 12px;/*定义字符间距，允许为负值，默认normal*/
    line-height: 40px;
    text-decoration: none;
    text-indent: 2em;/*首行缩进，可为负值，一般使用em，em为字符宽度的倍数*/
  }
    .two{
    word-spacing: 20px; /*定义英文单词之间的间距*/
    text-decoration: underline;/*设置文本的下划线(underline)，上划线(overline)，删除线(line-through)，或没有装饰(normal)*/
    }
    #pi{
    text-decoration: line-through overline; /*text-decoration 后可以赋多个值*/
    text-align: center; /*水平对齐方式*/
    }

    img {
      vertical-align: middle;/*垂直对齐方式*/
    }
  </style>
</head>
<body>
<div>
  <p class="one">你好你好你好你好你好快乐大本营 <br/>
  号好大家否代理费家连锁店</p>
  <p class="two" id="pi">hello world</p>
</div>
<p><image src="../../../Downloads/1.jpg">大家好</p>

</body>
</html>
```

## 背景样式

背景样式的具体属性

background-color: 设置背景颜色,按照颜色的格式填写,比如red, #F00, rgb(255,0,0)
```html
background-color: red;
background-color: #F00;
```

background-image: 设置背景图片, url(图片路径)
```html
background-image: url("image/xxx.jpg);
```

background-repeat: 设置背景图片是否平铺，repeat,no-repeat,repeat-x,repeat-y。
```html
background-repeat: repeat-x;
```
background-position: 设置背景图片显示位置，可以使用top,bottom,left,right设置，也可以直接设置数值(x轴,y轴)
```html

background-position: top left;
background-position: center center;
background-position: 10px 15px;
```
background-attachement: 设置背景是否固定，fixed表示固定。
```html
background-attachement: fixed;
```

背景属性的综合写法

background: color image repeat position attachement;
```html
background: red url("image/xxx.png) repeat 10px 10px fixed;
```
```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <style>
  .one{
    background-color:pink; /*背景颜色设置同 颜色设置的格式*/
    color:blue;
    weight:200px;  /* 块级元素即使设置了宽高，也不影响其独占一行或几行。*/
    height:200px;
    background-image: url(../../../Downloads/1.jpg); /*背景图片会把背景颜色覆盖，如果背景图片比元素小，则重复摆放;大，则默认左上角 */
    background-repeat: no-repeat; /* 在背景图片比元素小时设置背景图片是否平铺，默认是向右向下都平铺*/
  }
  </style>
</head>
<body>
  <div class="one">
    背景设置
  </div>
  <span>居于div下面</span>
</body>
</html>
```
```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <style media="screen">
    p{
      width: 200px;
      height: 200px;
      background-color: orange;
      background-image: url(../../../Downloads/1.jpg);
      /*background-position: left bottom;*/ /*设置背景图片的显示位置，左下 */
      /*background-position: center center; */ /* 背景图片位置为水平居中，垂直居中*/
      background-position: -50px -40px;  /* 可以使用像素设置位置*/
      background-attachment: fixed;   /* 背景是否固定 ,背景图片固定住，上下滑动时会出现背景图片的不同位置*/
        }
        .one{
          width: 200px;
          height: 200px;
          /*背景属性的综合写法*/
          background: red url(../../../Downloads/2.jpg) no-repeat -20px -10px ;
        }
  </style>
</head>
<body>
<p class="one">阿坝擦的放假回家看里面你哦爬起日说图</p>
</body>
</html>
```
##  CSS 盒子模型
 
 **html中的任何一个元素都可以看作一个盒子，每个盒子都由内边距(padding)  外边距(margin) 边框(border) 和元素的内容 组成。**
 
 #### 边框属性
 
 边框属性的属性值有：
 1. 宽 
 2. 颜色  transparent为透明的
 3. 样式,常用样式有solid , dotted, dashed, double
 
 边框属性可单独设置，可综合设置,不管如何设置，样式是必不可少的,否则其他设置效果无效
 
 
 
 示例代码：
 ```html
 <head>
  <meta charset="UTF-8">
  <title>box盒子模型</title>
  <style media="screen">
    .f1{
      width: 300px;
      height: 200px;
      background-color: yellow;
      /*设置边框属性的三种方法*/


      /*方法一  border边框的综合设置  宽度 样式 颜色   样式是必不可少的*/
      /*border: 5px dotted red;
      border-color:red blue pink green;*/


      /*方法二   单独设置边框时，样式也必不可少*/
      border-top-width: 10px;
      border-top-style: solid;
      border-top-color: red;

      /*方法三  border另一种综合设置*/
      border-top:5px dotted black;

    }
  </style>
</head>
 ```
 **小技巧：** 设置边框为0的方法
 ```html
 border:0 none;
 ```
 
 
 #### 内边距padding属性
 
padding可单独设置也可综合设置,**注意**综合设置时，一定要遵从上，(右，下，左)的顺序
 
**注意** 修改padding时会改变盒子的大小
 
示例代码：
 
```html
 <head>
  <meta charset="UTF-8">
  <title>Document</title>
  <style>
  *{
    margin: 0px;
    padding: 0px;
  }
  .one{
    /*height width只是设置了内容的宽高*/
    
    height:100px;
    width:500px;
    
    
    /*修改padding(内边距)会影响盒子的大小,但盒子里内容不会占用padding*/

    /*padding-top:50px;
    padding-bottom:50px;
    padding-left:50px;
    padding-right:50px;*/
    
    /*上下左右都是50px*/
    /*padding:50px;*/

    /*对称关系，padding综合设置的顺序为上右下左*/
    padding:50px 40px;
    /*padding:50px 40px 30px;*/
    /*padding:50px 40px 30px;*/


        /*盒子阴影*/
    box-shadow:10px  10px  5px #abcdef;
    background: red;
  }
  </style>
</head>

```
  
 #### 外边距margin
 
 用法同padding
 
 **margin: 10px auto; 实现盒子水平居中**,**auto**只能实现水平居中
 
 **注意**
1.外边距可以使用负值，使相邻元素重叠。
2.可能会出现外边距合并情况
3.为了方便操作,可以用 * { margin:0; padding: 0}取消浏览器的默认属性
 
 **外边距合并问题**
 1. 两个同级元素外边距合并，**只能上下合并，且以最大值为准** 左右是叠加
 2. 嵌套元素外边距的合并，对于两个嵌套关系的块元素，如果父元素没有上内边距及边框，则父元素的上外边距会与子
 元素的上外边距发生合并，合并后的外边距为两者  中的较大者，即使父元素的上外边距为0，也会发生合并
 如果希望外边距不合并，可以为父元素定义1像素的上边框或上内边距
 
 
 示例代码：
 ```html
 <head>
  <meta charset="UTF-8">
  <title>Document</title>
  <style>
  * {
    margin:0px;
    padding:0px;
  }
  .f1,.f2{
    width:500px;
    height:100px;
    border:5px solid red;
  }
  /*上下外边距合并问题，取最大的值，作为上下间距*/
  .f1{
    margin-bottom:10px;
  }
  .f2{
    margin-top:50px;
    /*将左右边距设置为auto(只在左右方向有用)，可以实现在父元素内的水平居中*/
    /*margin: 10px auto;*/
  }
  .f3{
    width:500px;
    height: 300px;
    background-color: red;
    margin-top: 10px;

    /*解决嵌套外边距合并问题，2种方法  子元素f4里margin属性必须有*/

    /*方法一*/
    /*padding-top: 1px;*/
    /*方法二*/
    border-top: 5px solid yellow;
  }
  .f4{
    width: 200px;
    height: 100px;
    margin: 50px auto;
    background-color: green;
  }

  </style>
</head>
<body>
  <div class="f1">来看待赛冠军落实党风建设力度咖啡</div>
  <div class="f2">打开了改进了开设的废旧塑料打法</div>
  <div class="f3">
    <div class="f4">

    </div>
  </div>
</body>
 ```
#### 盒子模型的其他属性

1. box-shadow 为盒子添加阴影
2. border-radius 圆角边框
3. border-image 用图片来创建边框
 
## CSS定位
### 浮动


元素的浮动是指设置了浮动属性的元素会脱离标准文档流的控制，移动到其父元素中指定位置的过程。比喻：游泳池的池底以及水面游泳池的池底相当于标准流
（文档流），水面相当于浮动的元素所有“层”。水面的元素会遮挡水中的元素)。

**格式**

```html
选择器 {
float: 属性值；
}
```

float的属性值可以为left, right, none.


示例代码：

```html
<head>
  <meta charset="UTF-8">
  <title>float浮动</title>
  <style media="screen">
    *{
      margin: 0;
      padding: 0;
    }
    .nav{
      /*去掉项目符号*/

      list-style: none;
      /*
      ul 的所有子元素都浮动了，但是ul又没有设置高度，那么ul的高度就变为0
      会导致后边的标准流元素也跟着移动，会对页面布局产生影响        */
    }
    .nav li{
      background-color: pink;
      float: left;
      margin: 10px;

    }

  </style>
</head>
```
```html
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <style media="screen">
    .f1{
      width: 300px;
      height: 200px;
      background-color: red;
      float: left;
    }
    .f2{
      width: 500px;
      height: 200px;
      background-color: blue;
/* 设置浮动时，需要注意它前一个元素是否有浮动，上一个元素无浮动的话，则此元素不浮动，
上设置浮动，此元素不设置浮动，此会被覆盖  ，上设置浮动，此有浮动，会在一行显示*/
/*元素变为行内块元素，具有行和块的特点*/
      float: left;
    }
  </style>
</head>
```

### 消除浮动

**浮动的影响**

**消除浮动的方法**

1. 给父元素设置一个高度
2. 在发生浮动的父元素最后添加一个空元素，给空元素设置clear属性，属性值有left，right，both
3. 直接给父元素设置overflow属性  。 overflow:hidden;
4. 最方便快捷的方法，使用伪元素


示例代码：

```html
<head>
  <meta charset="UTF-8">
  <title>消除浮动的影响</title>
  <style media="screen">
    *{
      margin: 0;
      padding: 0;
    }
    
    /*伪元素*/
    .clearfix::after, .clearfix::before {
      content: ""; /*内容必须设置*/
      height: 0;
      display: block;
      visibility: hidden;
      line-height: 0;
      clear: both;
    }
     /*第四种消除浮动的方法  使用伪元素*/
    .clearfix {
      zoom: 1;
     }
     
     
     
    .nav{
      list-style: none;

      /*第一种消除浮动的方法*/
      /*height: 50px;*/
      /*第二种消除浮动的方法*/
      /*overflow: hidden;*/

    }
    .nav li{
      background: red;
      width: 100px;
      height: 50px;
      text-align: center;
      line-height: 50px;   /*line-height = height 使字体垂直居中*/
      margin-right:10px;

      float: left;
    }

    /*第三种消除浮动的方法*/
    /*.nav div{
      clear: both;
    }*/
  </style>
</head>
```
## 定位position

常用属性值
1. static,默认值    **没有脱离标准流**
2. relative 相对定位  **没有脱离标准流**
3. absolute 绝对定位 **脱离了标准流**
4. fixed 固定，以浏览器可视窗口进行定位，不会随着滚动条移动 **脱离了标准流**

其中，absolute有三种情况：

1. 如果盒子没有body之外其他的祖先元素，那么在绝对定位的时候这个位置是相对于body的。

2. 如果盒子有祖先元素，但是祖先元素并没有设置定位，那么在绝对定位的时候这个位置还是相对于body的。

3. 如果盒子有祖先元素并且祖先元素有定位(absolute,relative都可以)，那么这个时候我们的盒子定位是相对于最近一个设置过定位的祖先元素的。

示例代码：
```html
  <style media="screen">
    .f1{
      width: 300px;
      height: 200px;
      background-color: red;
      /*相对于自己的位置发生偏移 */
      /*相对定位*/
      position: relative;

      top: 30px;  /*距离原先的顶部距离为30px*/
      left:30px;  /*距离原先距离的左距离为30px*/
    }


    /**/
    .f2{
      width: 500px;
      height: 300px;
      background-color: green;


      /*绝对定位
      该元素脱离了标准流
      f2 的父元素为body ，那么它的绝对定位都是相对于body的*/
      position: absolute;
      top: 100px;
      left: 200px;
    }
    .f3{
      width: 400px;
      height: 200px;
      background-color: blue;
      position: absolute;
      top: 50px;
      left: 50px;

    }
    .s{
      width: 100px;
      height: 100px;
      background-color: pink;

      /*
      1. 对s设置了absolute，但是s的祖元素都没有设置position
      那么，s绝对定位是相对于body

      2. 对s设置了absolute，同时s 的某一个祖先元素设置过position
      那么，s 的绝对定位都是相对于最近设置过定位的祖先
      */
      position: absolute;
      top: 10px;
      left: 10px;

    }
  </style>
```

### 子盒子在父盒子中居中的方法
1. 子盒子中用 magin:0px auto; // 调节0px使其上下居中，**前提**是父盒子中必须设置 **border**或**padding**属性

示例代码：
```html
<style media="screen">
    .f {
      width: 300px;
      height: 200px;
      background: yellow;
      /*border: 1px solid white;*/
      padding: 1px;
    }
    .s {
      width: 200px;
      height: 100px;
      background: pink;
      margin: 47px auto;
    }
  </style>
```

2. 给父盒子直接设置padding属性，为让子盒子居中，设置padding后，父的宽高做相应变化

示例代码：
```html
<style media="screen">
    .f {
      width: 200px; /*原宽300*/
      height: 100px;/*原高200*/
      background: yellow;

      padding: 100px;
    }
    .s {
      width: 200px;
      height: 100px;
      background: pink;

    }
  </style>
```

3. 给父盒子和子盒子设置**position**属性
* 子盒子绝对定位，通过调节子盒子里top和left的px值

* 在不知道父盒子大小的情况下进行定位


示例代码：

```html
<style media="screen">
  /*在不改变父元素大小的情况下，让子元素居中*/
    .f{
      width: 500px;
      height: 300px;
      background: yellow;
      margin: 50px auto;

     /*第一种 居中方法 */
      /*为让子盒子居中，设置padding后，父的宽高做相应变化400,200，保证父最后宽高不改变*/
      /*padding-left: 100px;
      padding-top: 100px;*/


      position: relative;
    }
    .s{
      width: 300px;
      height: 100px;
      background: red;

     /*第二种方法*/
     /*分别在父子元素设置定位属性，通过调节子元素里的px值 */
      position: absolute;
      /*top: 93px;
      left: 99px;*/

      /*第三种方法*/
      top: 50%;  /* 50% 是相对于父元素*/
      margin-top: -50px; /*向上移动元素本身高度的一半*/
      left: 50%;
      margin-left: -150px;

    }
     .d {
       width: 500px;
       height: 300px;
       background: yellow;
       padding-top: 1px;
     }

  .d  .v{
      width: 300px;
      height: 100px;
      background: red;
      /*margin: 00px auto;*/
      margin-top: 100px;
    }
  </style>
```

### 其它属性


1. overflow

overflow值 | 含义
----------|------|
hidden   | 超出隐藏部分
scroll  |超出部分显示滚动条
auto  | 超出部分显示滚动条，否则不显示
 
2. 伪元素
伪元素里必须要有content属性
示例代码：


```html
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <style media="screen">

  
    .f::before{
      content: "显示在span前面";
    }
    .f::after{
      content: "显示在span后面";
    }
  </style>
</head>
<body>
  <div class="f1">
    <span>闪客帝国几十块登录</span>
  </div>
</body>
```
3. display
属性值：

* block 显示为块元素，

* inline 显示为行元素

* inline-block 显示为行内块元素

示例代码：

```html
<style media="screen">

    /*display属性可以让块元素和行元素互相转换*/
    /*将俩个元素设置为行内块元素时，会底部在统一水平线水平对齐*/
    .f{
      width: 100px;
      height: 100px;
      background: blue;

      /*将块元素转化为行元素，如果块元素里没有内容，此时转化成的行元素就为空，会被后面的元素覆盖*/
      /*display: inline;  */

      display: inline-block;
    }
    .s{
      width: 100px;
      height: 200px;
      background: red;
      display: inline-block;
    }
    .c {
      width: 300px;
      height: 100px;
      background: pink;
      display: block;
    }

  </style>
```

4. visibility可视
属性值:
* hidden 隐藏一个元素，占据页面空间

* visible 页面是可视的

示例代码：

```html
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <style media="screen">
  .f{
    width: 100px;
    height: 100px;
    background: blue;
    /* 隐藏一个元素，占据页面空间 */
    /*visibility: hidden;*/

    /*隐藏一个元素，不占据页面空间*/
    display: none;
  }
  .s{
    width: 100px;
    height: 200px;
    background: red;
    display: inline-block;
  }
  </style>
</head>

```

5. z-index用于设置元素的层级
默认情况下，设置**定位**的元素层级比普通元素要高，是大于0，但是小于1

示例代码:

```html
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <style media="screen">
  .f1{
    width: 100px;
    height: 100px;
    background: blue;
    position: absolute;
    top: 0;
    left: 0;

    /*用于设置元素的层级，可以是任意整数*/
                /*默认情况下，设置定位的元素的层级都比普通元素的层级要高，是大于0，但是小于1*/
    			/*z-index: -1;*/
  }


  .f2{
    width: 300px;
    height: 200px;
    background: red;

    /*
			z-index的设置只对设置过定位的元素有效
			*/

    z-index: 1;
    position: relative;
  }
  .l{
    width: 300px;
    height: 100px;

    list-style: none;
  }

  /*
		浮动排列在一行的所有元素，默认情况下，元素的层级从左到右逐渐增大，
		从0开始无限接近于1
		*/

  .l li{
    width: 50px;
    height: 50px;

    margin-right: -1px;/*将相邻两个盒子边框显示为一条，*/
    border: 1px solid red;
    float: left;
  }
  .l li:hover{
    border-color: yellow;

    /*通过设置z-index,但同时必须设置position .当点击盒子边框时，盒子所有边框都变色*/
    z-index: 2;
    position: relative;
  }
  </style>
</head>
<body>
  <div class="f1"></div>
  <div class="f2"></div>
  <ul class="l">
    <li></li>
    <li></li>
    <li></li>
    <li></li>
  </ul>
</body>

```


 
