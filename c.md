
# 格式化的输入/输出
### printf函数
* printf()函数是格式化输出函数, 一般用于向标准输出设备按规定格式输出信息。
* printf()函数的调用格式为: 
```md
    printf("<格式控制字符串>", <参量表>);
```
* 格式输出，它是c语言中产生格式化输出的函数（在 stdio.h 中定义）。用于向终端（显示器、控制台等）输出字符。格式控制由要输出的文字和数据格式说明组成。要输出的的文字除了可以使用字母、数字、空格和一些数字符号以外，还可以使用一些[转义字符](http://baike.baidu.com/item/%E8%BD%AC%E4%B9%89%E5%AD%97%E7%AC%A6)表示特殊的含义。
* 其中格式控制字符串用于指定输出格式。格式控制串可由格式字符串和非格式字符串两种组成。格式字符串是以%开头的字符串，在%后面跟有各种格式字符，以说明输出数据的类型、形式、长度、小数位数等。如：

  * “%d”表示按十进制整型输出；
  * “%ld”表示按十进制长整型输出；
  * “%c”表示按字符型输出等。


  非格式字符串原样输出，在显示中起提示作用。输出表列中给出了各个输出项，要求格式字符串和各输出项在数量和类型上应该一一对应。
  
  
### scanf函数
* scanf()函数是格式输入函数，即按用户指定的格式从键盘上把数据输入到指定的变量之中。与printf()函数一样，都被声明在头文件stdio.h里.
* scanf()函数调用的格式为：
```md
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