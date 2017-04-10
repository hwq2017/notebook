
# 格式化的输入/输出
## printf函数
* printf()函数是格式化输出函数, 一般用于向标准输出设备按规定格式输出信息。
* printf()函数的调用格式为: 
```c
    printf("<格式控制字符串>", <参量表>);
```
* 格式输出，它是c语言中产生格式化输出的函数（在 stdio.h 中定义）。用于向终端（显示器、控制台等）输出字符。格式控制由要输出的文字和数据格式说明组成。要输出的的文字除了可以使用字母、数字、空格和一些数字符号以外，还可以使用一些[转义字符](http://baike.baidu.com/item/%E8%BD%AC%E4%B9%89%E5%AD%97%E7%AC%A6)表示特殊的含义。
* 其中格式控制字符串用于指定输出格式。格式控制串可由格式字符串和非格式字符串两种组成。格式字符串是以%开头的字符串，在%后面跟有各种格式字符，以说明输出数据的类型、形式、长度、小数位数等。如：

  * “%d”表示按十进制整型输出；
  * “%ld”表示按十进制长整型输出；
  * “%c”表示按字符型输出等。


  非格式字符串原样输出，在显示中起提示作用。输出表列中给出了各个输出项，要求格式字符串和各输出项在数量和类型上应该一一对应。
  
  
## scanf函数
* scanf()函数是格式输入函数，即按用户指定的格式从键盘上把数据输入到指定的变量之中。与printf()函数一样，都被声明在头文件stdio.h里.
* scanf()函数调用的格式为：
```c
    scanf("<格式控制字符串>"，地址列表);
    scanf("%d", &a);
```
* 使用scanf函数时应注意的问题 :
 1. scanf函数中的“格式控制”后面应当是变量地址，而不应
   是变量名。 
 1. 如果在“格式控制”字符串中除了格式说明以外还有其他字符，
   则在输入数据时在对应位置应输入与这些字符相同的字符。 
 1. 在用“％c”格式输入字符时，空格字符和“转义字符”都作为
   有效字符输入 
 1. 在输入数据时，遇以下情况时认为该数据结束。
    1. 遇空格，或按“回车”或“跳格”（Tab）键；
    1. 按指定的宽度结束，如“％3d”，只取3列；
    1. 遇非法输入。
    
    
# 函数
## int sprintf函数
头文件：#include <stdio.h>

sprintf()函数用于将格式化的数据写入字符串，其原型为：
```c
    int sprintf(char *str, char * format [, argument, ...]);
```

【参数】str为要写入的字符串；format为格式化字符串，与printf()函数相同；argument为变量。

除了前两个参数类型固定外，后面可以接任意多个参数。而它的精华，显然就在第二个参数--格式化字符串--上。 printf()和sprintf()都使用格式化字符串来指定串的格式，在格式串内部使用一些以“%”开头的格式说明符（format specifications）来占据一个位置，在后边的变参列表中提供相应的变量，最终函数就会用相应位置的变量来替代那个说明符，产生一个调用者想要的字符串。

sprintf()最常见的应用之一莫过于把整数打印到字符串中，如：
```c
    sprintf(s, "%d", 123);  //把整数123打印成一个字符串保存在s中
    sprintf(s, "%8x", 4567);  //小写16进制，宽度占8个位置，右对齐
```

sprintf的作用是将一个格式化的字符串输出到一个目的字符串中，而printf是将一个格式化的字符串输出到屏幕。sprintf的第一个参数应该是目的字符串，如果不指定这个参数，执行过程中出现 "该程序产生非法操作,即将被关闭...."的提示。

sprintf()会根据参数format 字符串来转换并格式化数据，然后将结果复制到参数str 所指的字符串数组，直到出现字符串结束('\0')为止。关于参数format 字符串的格式请参考printf()

## system函数
在linux/unix里，就是**执行shell命令**



表头文件

```c
#include<stdlib.h>
```
**定义函数**


```c
int system(const char *command);
```
比如：
```c
system("cp file newfile");  完成文件的拷贝
```
实现cp命令:

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main(int argc, char *argv[]){
    char a[10] = "cp ";
    char b[10] = " ";
    char cmd[100];
    if(3 == argc)
    {
       strcpy(cmd, a);
       strcat(cmd, argv[1]);
       strcat(cmd, b);
       strcat(cmd, argv[2]);
       system(cmd);
    }
    else{
       printf("Error!\n");
    }
    return 0;
}
```



## fgets函数

**功能**:  就是一次读取一行,遇到'\n'就立刻返回. 当返回值为NULL时表示文件读取结束

fgets函数用来从文件中读入字符串。fgets函数的调用形式如下：fgets（str，n，fp）；此处，fp是文件指针；str是存放在字符串的起始地址；n是一个int类型变量。函数的功能是从fp所指文件中读入n-1个字符放入str为起始地址的空间内；如果在未读满n-1个字符之时，已读到一个换行符或一个EOF（文件结束标志），则结束本次读操作，读入的字符串中最后包含读到的换行符。因此，确切地说，调用fgets函数时，最多只能读入n-1个字符。读入结束后，系统将自动在最后加'\0'，并以str作为函数值返回。

如果使用fgets()读取某个文件，第一次读取的bufsize为5，而文件的第一行有10个字符（算上'\n'），那么读取文件的指针会偏移至当前读取完的这个字符之后的位置。也就是第二次再用fgets()读取文件的时候，则会继续读取其后的字符。而，如果使用fgets() 读取文件的时候bufsize大于该行的字符总数加2（多出来的两个，一个保存文件本身的'\n'换行，一个保存字符串本身的结束标识'\0'），文件并不会继续读下去，仅仅只是这一行读取完，随后指向文件的指针会自动偏移至下一行。

[[fgets百科]](http://baike.baidu.com/link?url=85CtmE5PgeAdVqto_dEHJT7Cr748mYEFBieKuREHF6WtYKYO2dBAiR26Un4Ew1EiERoTFoEF9Agn7X9DGTC2BK)

**函数原型**

```c
char *fgets(char *s, int size, FILE *stream);
```

**参数**

  * s :  用于存放读取的字符串(传递数组名即可)/字符型指针，指向用来存储所得数据的地址
       
  * size: 指定读取一次最多读取到的字节个数
      
  * stream: 文件结构体指针，将要读取的文件流(直接填写stdin即可) . 
      
      [[stdin标准输入]](http://baike.baidu.com/link?url=gP7CUsIqxkth8rJJYcOn-LhBbKI0uquvqau_FuCOnsC7dC6FnihU93xJBe_5ztJQCLgaXIG7OTIaWNUvbwRDeK)  
      
比如:
```c
fgets(buf, 64, stdin); 从标准输入读入一行 ,从键盘输入一行
```

**返回值**

1. 成功，则返回第一个参数buf；
1. 在读字符时遇到end-of-file，则eof指示器被设置，如果还没读入任何字符就遇到这种情况，则buf保持原来的内容，返回NULL；
1. 如果发生读入错误，error指示器被设置，返回NULL，buf的值可能被改变
      


## fprintf函数


**功能**: 将格式化语句输出到指定的流

fprintf()函数根据指定的format(格式)发送信息(参数)到由stream(流)指定的文件. fprintf()只能和printf()一样工作. fprintf()的返回值是输出的字符数,发生错误时返回一个负值.

printf( )会根据参数format 字符串来转换并格式化数据, 然后将结果输出到参数stream 指定的文件中, 直到出现字符串结束('\0')为止。

**函数原型**:
```c
int fprintf (FILE* stream, const char*format, [argument])
```
FILE*stream：文件指针

const char* format：输出格式

[argument]：附加参数列表


**函数范例**

```c
#include <stdio.h>
int main(void) {
    FILE *FSPOINTER;
    char STRBUFF[16] = "Hello World.";
    //...
    FSPOINTER = fopen("HELLO.TXT", "w+");
    //...
    fprintf(FSPOINTER, "%s", STRBUFF);
    //...
    return 0;
}
```
输出至文件HELLO.TXT：

Hello World


## atoi函数

**功能**: 是把字符串转换成整型数的一个函数

atoi( ) 函数会扫描参数 nptr字符串，跳过前面的空白字符（例如空格，tab缩进等，可以通过isspace( )函数来检测），直到遇上数字或正负符号才开始做转换，而再遇到非数字或字符串结束时('\0')才结束转换，并将结果返回。如果 nptr不能转换成 int 或者 nptr为空字符串，那么将返回 0 。

**函数原型**
```c
int atoi(const char *nptr);
```
char *nptr : 需要转换的字符串

**代码实例**

```c
#include <stdio.h>

int main(void)
{
   int n;
   char *str = "12345.45";
   n = atoi(str);
   printf("n = %d\n", n);
   return 0;
}
```
输出:

n = 12345



# 指针

## 指向指针的指针

[指向指针的指针](https://wenku.baidu.com/view/11cc8625ccbff121dd36836e.html)


## 指针数组

**指针数组**就是一个数组，数组里的每一个元素均为指针

 **例如** :*p[2]是指针数组，实质是一个数组，里面的两个元素都是指针， []的优先级比*的优先级高，p先与[]结合,形成数组p[2],有两个元素的数组，再与*结合，表示此数组是指针类型的，每个数组元素相当于一个指针变量
 
**与二维数组对比**

二维数组: 如char string[10][10]只要定义了一个二维数组，无论赋不赋值，系统都会给他分配相应的空间，而且该空间一定是连续的。其每个元素表示一个字符，我们可以通过指定下标对其元素进行修改。

指针数组: 如char *str[5]系统至少会分配5个连续的空间用来存储5个元素，表示str是一个5个元素的数组，每个元素是一个指向字符型数据的一个指针
 
char a[3][8]={"gain","much","strong"};

char *n[3]={"gain","much","strong"};

![123](https://imgsa.baidu.com/baike/c0%3Dbaike72%2C5%2C5%2C72%2C24/sign=2885efa79f3df8dcb23087c3ac7819ee/a8ec8a13632762d0af4945efa0ec08fa513dc66f.jpg)


他们在内存的存储方式分别如右图所示，可见，系统给数组a分配了3×8的空间，而给n分配的空间则取决于具体字符串的长度。此外，系统分配给a的空间是连续的，而给n分配的空间则不一定连续.

由此可见，相比于比二维字符数组，指针数组有明显的优点：一是指针数组中每个元素所指的字符串不必限制在相同的字符长度；二是访问指针数组中的一个元素是用指针间接进行的，效率比下标方式要高。 但是二维字符数组却可以通过下标很方便的修改某一元素的值，而指针数组却无法这么做。
    
   
    
 
 
## 数组指针
 
**数组指针**是指向数组首元素的地址的指针，其本质为指针（这个指针存放的是数组首地址的地址，相当于2级指针，这个指针不可移动）
 

## 指针函数
一个函数不仅可以带回一个整型数据的值，字符类型值和实型类型的值，还可以带回指针类型的数据，使其指向某个地址单元。

**返回指针的函数，一般定义格式为**： 

类型标识符    *函数名(参数表)
```c
int *f(x，y); 
```
其中x，y是形式参数，f是函数名，调用后返回一个指向整型数据的地址指针。f(x，y)是函数，其值是指针。 

## 函数指针
指向函数代码首地址的指针变量称为函数指针
函数指针是用来存放函数的地址，这个地址是一个函数的入口地址，而且是函数调用时使用的起始地址。
当一个函数指针指向了一个函数，就可以通过这个指针来调用该函数，函数指针可以将函数作为参数传递给其他函数调用。
 
 1. **函数指针定义**
 
 函数类型  (*指针变量名) (形参列表)
 
 例如：
 ```c
 int (*f)(int x)
 ```
 **注意**：
 
 函数指针和它指向的函数的参数个数和类型都应该是—致的； 函数指针的类型和函数的返回值类型也必须是一致的。
 
2. **函数指针的赋值**

函数名和数组名一样代表了函数代码的首地址，因此在赋值时，直接将函数指针指向函数名就行了。
```c
例如， 
int func(int x);   /* 声明一个函数 */ 
int (*f) (int x);    /* 声明一个函数指针 */ 
f=func;            /* 将func函数的首地址赋给指针f */
```
赋值时函数func不带括号，也不带参数，由于func代表函数的首地址，因此经过赋值以后，指针f就指向函数func(x)的代码的首地址。

3. **通过函数指针调用函数**

函数指针是通过函数名及有关参数进行调用的
 
与其他指针变量相类似，如果指针变量pi是指向某整型变量i的指针，则*p等于它所指的变量i；如果pf是指向某浮点型变量f的指针，则*pf就等价于它所指的变量f。同样地，*f是指向函数func(x)的指针，则*f就代表它所指向的函数func。所以在执行了f=func;之后，(*f)和func代表同一函数。 
由于函数指针指向存储区中的某个函数，因此可以通过函数指针调用相应的函数。现在我们就讨论如何用函数指针调用函数，

它应执行下面三步： 

**首先**，要说明函数指针变量。
```c
例如：int (*f)(int x); 
```
**其次**，要对函数指针变量赋值。
```c
例如： f=func;    (func(x)必须先要有定义)
```
**最后**，要用 (*指针变量)(参数表);调用函数。
```c
例如：    (*f)(x);(x必须先赋值) 
```


## 函数指针数组

函数指针数组是一个其元素是函数指针的数组



# 结构体

### 结构体变量的声明及初始化
方法一和方法二是通过对结构类型命名的方式进行变量的声明和初始化

**方法一**
```c
struct A{
    int a;
    float b;
    char ch[4];
    char c;
};
struct A  a = {1, 2.2, {1,2,2,2}, 'c'};  //  struct不能省略!!!      可以在struct前加  typedef
```
**typedef**的使用
```c
typedef struct {
    int a;
    float b;
    char ch[4];
    char c;
}A;    //  注意： 类型A的名字必须出现在定义的末尾，而不在struct的后面,如果struct后面有如S就是将S重新命名为A
A a = {1, 2.2, {1,2,2,2}, 'c'};
```
**方法二**

```c
struct A{
    int a;
    float b;
    char ch[4];
    char c;
}a = {1, 2.2, {1,2,2,2}, 'c'}; 
struct A b;
b.a = 2;    // 不仅可以通过这种方式进行对变量的初始化，还可以通过这种方式获得结构体成员的值
b.b = 5.6;
b.c = 'x';
```
以下这种初始化方式是不对的,因为数组的名即数组的首地址是个常量
```c
b.ch = "nihao";  b.ch = {'a','s','d','f'}; 
```
可以采用以下方式:
```c
strcpy(b.ch, "nihao");
```

**方法三**

适合临时使用
```c
struct {
    int a;
    float b;
    char ch[4];
    char c;
}a = {1, 2.2, {1,2,2,2}, 'c'}; 
```

### 结构类型的实际参数和返回值

函数可以有结构类型的实际参数和返回值

1. 结构体类型变量可以作为函数的实参,  **注意**必须将结构体声明为全局变量，即在main函数之外声明
```c
#include <stdio.h>

struct S{
    char *name;
    int age;
};
void print(struct S a);
 int main(int argc, const char *argv[])
 {
    struct S stu={"ton", 14};
   print(stu);
   
     return 0;
 }
void print(struct S a)
{
    printf("%s\n", a.name);
    printf("%d\n", a.age);
}
```
2. 函数返回类型为结构体  **注意**，函数print的形式参数名和结构S的成员名相同是合法的，因为结构的名字拥有自己的空间。

```c
#include <stdio.h>

struct S{
    char *name;
    int age;
    float score;
};
struct S print(char *name, int age, float score);

int main(int argc, const char *argv[])
{
   struct S stu;
   stu = print("sam", 11, 78);
   printf("%s  %d  %f\n", stu.name, stu.age, stu.score);
    return 0;
}
struct S print(char *name, int age, float score)
{
    struct S a;
    a.name = name;
    a. age = age;
    return a;
}
```
### 结构体数组

**结构体数组就是具有相同结构类型的变量的结合**

代码示例：
```c
#include <stdio.h>

int main(int argc, const char *argv[])
{
    struct S{
        char name[20];
        int age;
        float score;
    };
    struct S stu[5]={
        {"tom", 12, 90},
        {"san", 13, 89},
        {"lili", 12, 99},
        {"vivi", 13, 78},
        {"ti", 12, 90},
    };
    int i;
    for(i = 0; i < 5; i++)
    {
    printf("%-5s%-5d%-5f\n", stu[i].name, stu[i].age, stu[i].score);
    }
    retutn 0;
}
```

### 结构体指针(指向结构体的指针)

1. 定义结构体的指针

```c
struct 结构体名  *指针名;
```
如：
```c
struct A{                                                                                
   int age;                                    
   char *name;                                  
};                                              
struct A s;                                     
struct A *p;                                    
p = &s;     // 将结构变量s的首地址赋值给指针变量 p  
```                                             
2. 用指针访问结构体成员：  (*p).name
 
3. 用指针直接访问结构体成员可以用 " -> " 符号
如：  p->name
 
以下三条语句均是等价的
 ```c
 s.name="san";  (*p).name="san";  p->name="san";
 ```
4.
```c
typedef struct A{                                       
   int age;                                    
   char *name;                                 
}*p, a;          //  struct A * =======>p       如果没有 A 即 struct * =====> p                            
 a s={12,"li"};
 p q;  //定义指针变量 q ;
 q = &s;  
```

### 嵌套的结构体
即一种结构嵌套在另一种结构中使用
 
# 预处理命令

## 宏定义

宏定义不是C语句，不需要在末尾加分号， 宏定义是专门用于预处理命令的一个专用名词，它与定义变量的含义不同，只做字符替换，不分配内存空间。

### 1. 不带参数的宏定义

一般形式为

```c
#define PI 3.1415926     //  PI 成为"宏名"，一般大写
```
就是用标识符PI 代替字符串 "3.1415926",在程序预编译(预处理)时，将程序中在次命令之后的所有的PI 都用"3.1415926" 替换。

(1)**注意**

宏定义是用宏名代替一个字符串，只是做简单的置换，不做正确性的检查。

如果

```c
#define PI 3.14i926
```
将数字1写成字母i，在预处理时是正常带入，不管含义是否正确，只有在编译时才会发现错误并报错。

(2) #define命令出现在程序中函数的外面，宏名的有效范围为定义命令之后到本源文件结束。通常，#define 命令写在文件开头，函数之前，作为文件一部分，在此文件范围内有效。


(3) 可以使用 #undef 命令终止宏定义的作用域。


(4) 在进行宏定义时，可以引用已定义的宏名，可以层层置换

例如:
```c
#include <stdio.h>

#define R 3.0
#define PI 3.1415926
#define L 2*PI*R
#define S PI*R*R

int main(int argc, const char *argv[])
{
    printf("L = %f\nS = %f\n", L, S);
    return 0;
}
```
```c
运行结果:
L = 18.849556
S = 28.274333
```

**注意：**
程序中用括号括起来的引号里额字符串中的字符，即使与宏名相同，也不做替换。


## 带参数的宏定义

定义形式：
```c
#define 宏名(参数表) 字符串
```

例如：

```c
#define S(a,b) a*b
area = S(3,2);
```

对带参的宏定义，按照宏命令中指定的字符串从左到右依次置换，如S(3,2),将程序中相应的实参代替宏定义中的形参，将3，2分别代替a, b， 用3 * 2代替S(3,2)，宏定义中的字符串中的字符不是参数字符的(例如 a * b 中的 * )则保留.


**注意**

```c
#define PI 3.1415926
#define S(r) PI*r*r

area = S(a+b)
```
a+b 替换 r,  S(a+b) 即为 PI*a+b*a+b, 显然这样是错误的，所以我们在宏定义时要这样写 
```c
#define S(r) PI*(r)*(r)
```
其次，还要注意 ，带参的宏定义时， 宏名和带参数的括弧之间不应加空格。


**带参的宏定义与函数的区别**

1. 函数调用时，先求出实参表达式的值，然后带入形参。而使用带参的宏只是进行简单的字符替换

1. 函数调用是在程序运行时处理的，分配临时的内存单元，而宏展开则是在预处理时进行的，并不分配内存单元，也不进行值传递，也没有返回值。

1. 对函数中，实参和形参都要定义类型，而且类型要一致，否则进行类型转换。而 宏名无类型，参数也无类型。宏定义时，字符串可以是任意类型的数据。

1. 调用函数只可得到一个返回值，而用宏可以设法得到几个结果。

```c
#include <stdio.h>

#define PI 3.1415926
#define CIRCLE(R,L,S,V) L = 2*PI*R; S = PI*R*R; V = 4.0/3.0*PI*R*R*R

int main(int argc, const char *argv[])
{
    float r, l, s, v;
    scanf("%f", &r);
    CIRCLE(r,l,s,v);
    printf("r = %6.2f,l = %6.2f,s = %6.2f,v = %6.2f\n", r, l, s, v);
    return 0;
}
```
经预编译宏展开后的程序如下:

```c
int main(int argc, const char *argv[])
{
    float r, l, s, v;
    scanf("%f", &r);
    l = 2*3.1415926*r; s = 3.1415926*r*r; v = 4.0/3.0*3.1415926*r*r*r;
    printf("r = %6.2f,l = %6.2f,s = %6.2f,v = %6.2f\n", r, l, s, v);
    return 0;
}
```
```c
运行结果:
3
r =   3.00,l =  18.85,s =  28.27,v = 113.10
```

5. 使用宏次数多时，宏展开后源程序长，因为每展开一次都使程序增长，而函数调用不使源程序增长。

6. 宏替换不占运行时间，只占编译时间，函数调用则占用运行时间(分配单元， 保留现场，值传递，返回)。


## 文件包含

就是一个源文件可以将另外一个源文件的全部内容包含进来，c语言中用 #include 命令实现文件包含的操作，

```c
#include <文件名>   // 尖括号表示是 系统到存放 C 库函数的头文件所在目录中寻找要包含的文件，属于标准方式
或
#include "文件名"  // 双引号表示 用户自己编写的文件
```

1. 一个 #include 命令 只能指定一个被包含文件，如果要包含n个文件，要用 n 个inclue 命令
2. 如果文件1 包含 文件2 ，而文件2中**要用到**文件3的内容，则可在文件1中这样写：
```c
#include "file3.h"
#include "file2.h"  // 文件3要在文件2之前
```
**也可以这样**，将文件3 包含到 文件2 中，在将文件2 包含到文件1中。


## 条件编译

对一部分内容指定编译条件
**条件编译命令有以下几种形式：**

1. 
```c
#ifdef 标识符
程序段 1
#else
程序段 2
#endif
```
例如：
```c
#include <stdio.h>

#define LETTER1

int main(int argc, const char *argv[])
{
    char str[20] = "CLanguage", c;
    int i = 0;
    while((c = str[i]) != '\0')
    {
#ifdef LETTER1
        if(c >= 'a' && c <= 'z')
            c = c - 32;
#else
        if(c >= 'A' && c <= 'Z')
            c = c + 32;
#endif
        printf("%c", c);
        i++;
    }
    printf("\n");
    return 0;
}
```

它的作用是当所指定的标识符已经被 #define 命令定义过，则在程序编译阶段只编译程序段1，否则编译程序段2。其中 #else 部分可以省略。

2. 
```c
#ifndef 标识符
程序段 1
#else
程序段 2
#endif
```

它的作用是当所指定的标识符未被定义过，则在程序编译阶段只编译程序段1，否则编译程序段2。

3.
```c
#ifndef 表达式
程序段 1
#else
程序段 2
#endif
```

当表达式的值为真时就编译程序段1，否则编译程序段2。








