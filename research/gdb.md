    编写代码过程中少不了调试。在windows下面，我们有visual studio工具。在linux下面呢，实际上除了gdb工具之外，你没有别的选择。那么，怎么用gdb进行调试呢？我们可以一步一步来试试看。
```
#include <stdio.h>

int iterate(int value)
{
    if(1 == value)
        return 1;

    return iterate(value - 1) + value;
}

int main()
{
    printf("%d\n", iterate(10));
    return 1;
}
```
    既然需要调试，那么生成的可执行文件就需要包含调试的信息，这里应该怎么做呢？很简单，输入 gcc test.c -g -o test。输入命令之后，如果没有编译和链接方面的错误，你就可以看到 可执行文件test了。
    调试的步骤基本如下所示，

（01） 首先，输入gdb test
（02） 进入到gdb的调试界面之后，输入list，即可看到test.c源文件
（03） 设置断点，输入 b main
（04） 启动test程序，输入run
（05） 程序在main开始的地方设置了断点，所以程序在printf处断住
（06） 这时候，可以单步跟踪。s单步可以进入到函数，而n单步则越过函数
（07） 如果希望从断点处继续运行程序，输入c
（08） 希望程序运行到函数结束，输入finish
（09） 查看断点信息，输入 info break
（10） 如果希望查看堆栈信息，输入bt
（11） 希望查看内存，输入 x/64xh + 内存地址
（12） 删除断点，则输入delete break + 断点序号
（13） 希望查看函数局部变量的数值，可以输入print + 变量名
（14）希望修改内存值，直接输入 print  + *地址 = 数值
（15） 希望实时打印变量的数值，可以输入display + 变量名
（16） 查看函数的汇编代码，输入 disassemble + 函数名
（17） 退出调试输入quit即可
