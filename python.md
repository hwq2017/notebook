
## python基础 

### 一.python特点

1. python是开源的（源代码开发，对语言发展有什么好处，GUN GPL）
2. python是面向对象的编程语言 （什么是面向对象，面向对象有什么好处，特点是什么，继承，封装，多态）
3. python思想简单，优美，清晰
4. 跨平台性，很够和很多语言进行很好的融合（强大的库将消息转码，多样性的解释器）
5. 动态编程语言，静态编程语言。强类型编程语言，弱类型编程语言。python是强类型的动态编程语言

### linux安装

1.下载解压

2.进入文件夹  sudo ./configure

3.安装  make    make install

4. /usr/local/bin 会有python的安装后可执行文件  将这个目录添加到环境变量
                                                或者将这个目录下的可移植性文件创建软连接到环境变量目录下
							
5. apt-get install ipython

6. python 官方第三方包管理程序  pip
```sh
   apt-get install python-pip 
   
   apt-get install python3-pip
   
   pip  install  SomePackage
   
   pip  install  --upgrade SomePackage
   
   pip uninstall SomePackage
   
	   show  search   list
```   
   pip freeze > requirements.txt  导出软件环境
   
   pip install -r requirements.txt   安装软件环境
   
   
    程序由模块构成 （在python中一个模块对应一个.py文件）
    模块包含语句
    语句包含表达式
    表达式建立并处理对象

	
1. 循环判断
```sh
if elif else for while break continue 
```
2. 逻辑表达式
```sh
and or is not in 
```
3. 函数模块类
```sh
from import as def pass lambda return class 
```

4. 异常
```sh
try except finally raise
```
5. 其他
```sh
del global with assert yield 
True  False  None  nonlocal ----> 3.x
exec  print                 ----> 2.x
```	
	
6. 数字  ： 整形1 2 3   浮点型1.2    科学计数法1.23e+10    复数a + bj
   

#### 输入输出
python 2

1. 输入input(...)

raw_input(...)


2. 输出 print 

python2    print  

python3    print（）

1.print 每一项都可以是 常量/变量
2.当输出多项的时候用逗号隔开，会自动添加空格
3.可以对字符串进行格式化输出
4.格式控制符的修饰符
5.换行问题 python2 结尾加 ，  python3 end = ''
6.向流中输出


#### 列表：

定义 ： []

元素 ： 可以是任意类型，包含构造类型

有序的集合

可变类型

支持  +   *  in


#### 元组
定义 ： （）

元素 ： 可以是任意类型，包含构造类型

有序的集合

不可变类型

支持  +   *  in



#### 字典
定义 ：{}

元素 ：键值对： 值可以是任意类型，包含构造类型，函数名
                键 不能重复，可以是整形，字符，字符串，浮点型可以是常量或者变量，通常字符字符串较多

无序的集合

可变类型

支持 ： in 

#### 集合
定义 ：{}

元素 ： 值可以是任意类型，包含构造类型，函数名，不能包含重复
                

无序的集合

可变类型  用frozenset可以创建一个不可变集合

支持  in -  | ^ &


数据类型 |  数字   |     字符串   |  列表   |  元组  |   字典    |    set集合  |   frozenset集合|
------- | --------|  -----------|   ------- |  ------|  -------|   ------ |-------|
有序性  |    xx    |     有序   |    有序  |   有序  |   无序   |     无序    |     无序|
可变性  |   不可变   |   不可变   |  可变  |   不可变   | 可变   |    可变     |    不可变 |
运算    |   数学运算  |  + * in  |   in  + * | in + *  | in   |     in -  & ^ |   in -  & ^|

### 类
### 魔法方法和属性

**魔法属性:** 
```sh
__doc__ (文档字符串), __class__ , __dict__ (类与对象的所有成员,类输出的是全局的函数,变量等信息,对象输出的是对象拥有的普通变量),
```
**魔法方法:** 
```sh
__getattr__ , __setattr__ ,__init__, __new__ , __call__(模拟函数行为) , __mro__(方法解析顺序)
```

```sh
class A(object):
    ''' magic 魔法方法 '''
    pass

a = A()

print a.__doc__
print a.__class__
print a.__dict__


class B(object):

    # 对象的初始化,一个实例方法,第一个参数是self
    def __init__(self):
        print '__init__ ...'
        self.dict = {}

    # 用于对象的创建,是一个静态方法,第一个参数为cls,执行完new后在执行init,且参数要一一对应
    def __new__(cls):
        print '__new__ ...'
        return super(B,cls).__new__(cls)

    #  当程序结束后,所有的实例都会被析构(垃圾回收机制),即调用此方法
    def __del__(self):
        print '__del__ ...'

    # 模拟函数的行为
    def __call__(self,n):
        print '__call__ ...',n


    # 如果 name 被访问,但同时它又不存在,就会调用此方法,从对象中读取某个属性时，首先需要从self.__dicts__中搜索该属性，再从__getattr__中查找。
    def __getattr__(self,name):
        print 'you use getattr'


    # 如果要给 name 赋值,就会调用此方法,设置对象的属性
    def __setattr__(self,name,data):
        print 'you use setattr'
        self.__dict__[name] = data
        print name

    # 用来删除对象的属性时调用
    def __delattr__(self,name):
        print 'you use delattr'


    #  用于索引操作,如字典. 分别表示获取,设置
    def __getitem__(self,key):
        return self.dict[key]
    def __setitem__(self,key,value):
        self.dict[key] = value

    # 返回元素的数量
    def __len__(self):
        return len(self.dict)

b = B()
b('hello')
b['a'] = 1     # 调用setitem
print b['a']   # 调用getitem
b.value
b.value = 5
del b.value
print len(b)
print b.__dict__
# print B.__dict__
```

### 内置函数

**locals()**:以dict类型返回当前位置的全部局部变量。
```sh
def fun():
    a = 1
    b = 2
    return locals()
print fun()
```

**glabals()**:以dict类型返回当前的全局变量(包括内置变量)。
```sh
def fun():
    a = 1
    b = 2
print globals()
```
**issubclass(class,class)**:判断是否有继承关系

**isinstance(obj,class or type or tuple)**:判断是否有继承关系

### python异常处理

1. try…except…
只看try和except的部分，如果没有出现异常则except后的语句在执行try语句后被忽略，如果try子句中发生异常，该部分的其他语句被忽略，直接跳到except部分，执行其后面指定的异常类型及其子句。except后面也可以没有任何异常类型，即无异常参数。这样无论try后面的语句发生什么异常都会执行except。except后如果同时扑捉多个异常则中间用逗号隔开。


2. 处理多个异常
所谓处理多个异常指的是捕获到不同的异常时可以用不同的语句模块进行处理。


3. finally和else语句
else语句是当执行了try语句后会执行else语句，每当程序出现异常，也就是执行了except语句那么else语句就不会执行了。
finally语句必须放在整个try…except..else..finally语句的最后。无论是否发生异常最后都会执行finally后面的语句块

4. raise用于显式地出发异常，其一般形式很简单，raise后面跟着一个类或者类的实例就可以了。如果你要自己创建一个类，那么这个类需要继承于Exception类。
```sh
class MyError(Exception):
    pass

try:
    s = None
    if s is None:
        print ("s 是空对象")
        #如果引发MyError异常，后面的代码将不能执行
        raise MyError("附加异常信息") 
    print (len(s))
except MyError as X:
    print ("空对象没有长度")
    print(X.args)
```

#### with ... as...

with expresion as variable的执行过程是，首先执行__enter__函数，它的返回值会赋给as后面的variable，想让它返回什么就返回什么，只要你知道怎么处理就可以了，如果不写as variable，返回值会被忽略。然后，开始执行with-block中的语句，不论成功失败(比如发生异常、错误，设置sys.exit())，在with-block执行完成后，会执行__exit__(type,value,traceback)函数。如果with代码块发生异常则__exit__中的参数会被置为相应的异常信息。如果__exit__函数返回值为假，则异常会重新引发，否则，异常会终止。如果with代码块没有发生异常则__exit__中的参数为None。

用这中方法可以用来简化try/finally代码，看起来可以比try/finally更清晰。这样的过程其实等价于：
```sh
    try:  
          执行 __enter__的内容  
          执行 with_block.  
    finally:  
          执行 __exit__内容  
```

### 模块,包

m1.py >> 顶层模块
```sh
#coding=utf-8

# 在非顶层模块(完成相应功能)中,一般不允许除函数,类之外的顶层代码出现,否则在导入该模块时就会执行该顶层代码
# 顶层模块(调用)

# 可以在一个import下同时导入多个模块,用 , 隔开, 允许多个模块下变量名相同
# import m2,m3

# 如果模块名太长,可以起别名
# import m2 as M

# 重复导入同一模块时,代码只执行一次,可以用内建函数 reload(模块名) 使重复执行,一般针对第三方模块
# import m2
# reload(m2)

import m2
import m3

# from import 用来将模块的部分属性导入到当前的命名空间,如果原来有重名的变量将会被覆盖
# * 将全部导入到当前命名空间
from m3 import *
# 导入模块中受保护成员,不能用 *,如下:
from m3 import _fun

m = m2.Demo('hello')
print m.getName()
print m2.fun(10,20)

m3.func()
m3._fun()



# 包的导入路径内每个目录必须有__init__.py文件,可以写入代码,也可以不写.这样就可以在__init__.py中导入我们所需要的模块

from package import ctime,fun # *

print ctime()
fun()

# 包的导入两种方式:

from package.p import fun
import package.package1.p1
# import package.p

fun()
package.package1.p1.fun()
# package.p.fun()

```
m2.py
```sh
#coding=utf-8

class Demo(object):
    def __init__(self,name):
        self.name = name
    def getName(self):
        return self.name


def fun(a,b):
    return a + b

# 在本模块中 __name__ == '__main__',导入到顶层模块中,__name__是导入的模块名
print '=====',__name__

if __name__ == '__main__':
    print '顶层代码,可以做代码测试'
```
m3.py
```sh
#coding=utf-8
def func():
    print 'hello m3'

def _fun():
    print '我是模块中受保护的成员'    

print 'm3m3m3m3' # 顶层代码

```






















   
   
   
   
