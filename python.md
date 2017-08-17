
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






























   
   
   
   
