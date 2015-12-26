Java 是一种可以撰写跨平台应用程序的面向对象的程序设计语言

JVM Java虚拟机 Java虚拟机包括一套字节码指令集、一组寄存器、一个栈、一个垃圾回收堆和一个存储方法域

Java SE（J2SE，Java2 Platform Standard Edition，标准版）

Java EE（J2EE，Java 2 Platform, Enterprise Edition，企业版）

Java ME（J2ME，Java 2 Platform Micro Edition，微型版）

JDK java develop kit (JAVA API包,编译开发是引用的包)

JRE java runtime environment(java程序运行的环境)

基本含义
--------

抽象类：规定一个或多个抽象方法的类别本身必须定义为abstract，抽象类只是用来派生子类，而不能用它来创建对象。

final类：又称“最终类”，它只能用来创建对象，而不能被继承，与抽象类刚好相反，而且抽象类与最终类不能同时修饰同一个类。

包：Java中的包是相关类和接口的集合，创建包须使用关键字package。

继承：Java作为面向对象编程语言，支持继承这基本概念。但Java只支持单根继承，java.lang.Object是所有其他类的基类。[4] 

多态类：在Java中，对象变量是多态的。而Java中不支持多重继承。

接口：Java中的接口是一系列方法的声明，是一些方法特征的集合，一个接口只有方法的特征没有方法的实现，因此这些方法可以在不同的
地方被不同的类实现，而这些实现可以具有不同的行为。

通用编程：任何类类型的所有值都可以同Object类型的变量来代替。

封装：把数据和行为结合起在一个包中，并对对象使用者隐藏数据的实现过程，一个对象中的数据叫他的实例字段（instance field）。

重载：当多个方法具有相同的名字而含有不同的参数时，便发生重载。编译器必须挑选出调用哪个方法进行编译。

重写：也可称为方法的“覆盖”。在Java中，子类可继承父类中的方法，而不需要重新编写相同的方法。但有时子类并不想原封不动地继承父
类的方法，而是想作一定的修改，这就需要采用方法的重写。值得注意的是，子类在重新定义父类已有的方法时，应保持与父类完全相同的方法头声明。

Class类：Object类中的getClass方法返回Class类型的一个实例，程序启动时包含在main方法的类会被加载，虚拟机要加载他需要的所有类，每一个加载的类都要加载它需要的类。

基本语法
--------

大小写敏感：Java是大小写敏感的，这就意味着标识符Hello与hello是不同的。

类名：对于所有的类来说，类名的首字母应该大写。如果类名由若干单词组成，那么每个单词的首字母应该大写，例如 MyFirstJavaClass。

方法名：所有的方法名都应该以小写字母开头。如果方法名含有若干单词，则后面的每个单词首字母大写，例如myFirstJavaMethod。

源文件名：源文件名必须和类名相同。当保存文件的时候，你应该使用类名作为文件名保存（切记Java是大小写敏感的），文件名的后缀为.java。（如果文件名和类名不相同则会导致编译错误）。

主方法入口：所有的Java 程序由public static void main(String [] args)方法开始执行。

Java关键字
----------


Java关键字
　　
abstract
抽象方法，抽象类的修饰符

assert
断言条件是否满足

continue
不执行循环体剩余部分

default
switch语句中的默认分支

do-while
循环语句，循环体至少会执行一次

double
64-bit双精度浮点数

else
if条件不成立时执行的分支

enum
枚举类型

extends
表示一个类是另一个类的子类

final
表示定义常量

finally
无论有没有异常发生都执行代码

float
32-bit单精度浮点数

for
for循环语句

goto
用于流程控制

if
条件语句

implements
表示一个类实现了接口

import
导入类

instanceof
测试一个对象是否是某个类的实例

int
32位整型数

interface
接口，一种抽象的类型，仅有方法和常量的定义

long
64位整型数

native
表示方法用非java代码实现

new
分配新的类实例

package
一系列相关类组成一个包

private
表示私有字段，或者方法等，只能从类内部访问

protected
表示保护类型字段

public
表示共有属性或者方法

return
方法返回值

short
16位数字

static
表示在类级别定义，所有实例共享的

strictfp
浮点数比较使用严格的规则

super
表示基类

switch
选择语句

synchronized
表示同一时间只能由一个线程访问的代码块

this
调用当前实例或者调用另一个构造函数

throw
抛出异常

throws
定义方法可能抛出的异常

transient
修饰不要序列化的字段

try
表示代码块要做异常处理

void
标记方法不返回任何值

volatile
标记字段可能会被多个线程同时访问，而不做同步

while
while循环


主要特性
--------

Java语言是易学的。Java语言的语法与C语言和C++语言很接近，使得大多数程序员很容易学习和使用Java。另一方面，Java丢弃了C++中很少使用的、很难理解的、令人迷惑的那些特性，如操作符重载、多继承、自动的强制类型转换。特别地，Java语言不使用指针，而是引用。并提供了自动的废料收集，使得程序员不必为内存管理而担忧。

Java语言是强制面向对象的。Java语言提供类、接口和继承等原语，为了简单起见，只支持类之间的单继承，但支持接口之间的多继承，并支持类与接口之间的实现机制（关键字为implements）。Java语言全面支持动态绑定，而C++语言只对虚函数使用动态绑定。总之，Java语言是一个纯的面向对象程序设计语言。

Java语言是分布式的。Java语言支持Internet应用的开发，在基本的Java应用编程接口中有一个网络应用编程接口（java net），它提供了用于网络应用编程的类库，包括URL、URLConnection、Socket、ServerSocket等。Java的RMI（远程方法激活）机制也是开发分布式应用的重要手段。

Java语言是健壮的。Java的强类型机制、异常处理、垃圾的自动收集等是Java程序健壮性的重要保证。对指针的丢弃是Java的明智选择。Java的安全检查机制使得Java更具健壮性。

Java语言是安全的。Java通常被用在网络环境中，为此，Java提供了一个安全机制以防恶意代码的攻击。除了Java语言具有的许多安全特性以外，Java对通过网络下载的类具有一个安全防范机制（类ClassLoader），如分配不同的名字空间以防替代本地的同名类、字节代码检查，并提供安全管理机制（类SecurityManager）让Java应用设置安全哨兵。

Java语言是体系结构中立的。Java程序（后缀为java的文件）在Java平台上被编译为体系结构中立的字节码格式（后缀为class的文件），然后可以在实现这个Java平台的任何系统中运行。这种途径适合于异构的网络环境和软件的分发。

Java语言是可移植的。这种可移植性来源于体系结构中立性，另外，Java还严格规定了各个基本数据类型的长度。Java系统本身也具有很强的可移植性，Java编译器是用Java实现的，Java的运行环境是用ANSI C实现的。[8] 

Java语言是解释型的。如前所述，Java程序在Java平台上被编译为字节码格式，然后可以在实现这个Java平台的任何系统中运行。在运行时，Java平台中的Java解释器对这些字节码进行解释执行，执行过程中需要的类在联接阶段被载入到运行环境中。

Java是性能略高的。与那些解释型的高级脚本语言相比，Java的性能还是较优的。

Java语言是原生支持多线程的。在Java语言中，线程是一种特殊的对象，它必须由Thread类或其子（孙）类来创建。通常有两种方法来创建线程：其一，使用型构为Thread(Runnable)的构造子将一个实现了Runnable接口的对象包装成一个线程，其二，从Thread类派生出子类并重写run方法，使用该子类创建的对象即为线程。值得注意的是Thread类已经实现了Runnable接口，因此，任何一个线程均有它的run方法，而run方法中包含了线程所要运行的代码。线程的活动由一组方法来控制。Java语言支持多个线程的同时执行，并提供多线程之间的同步机制（关键字为synchronized）。

Java语言是动态的。Java语言的设计目标之一是适应于动态变化的环境。Java程序需要的类能够动态地被载入到运行环境，也可以通过网络来载入所需要的类。这也有利于软件的升级。另外，Java中的类有一个运行时刻的表示，能进行运行时刻的类型检查。

Java语言的优良特性使得Java应用具有无比的健壮性和可靠性，这也减少了应用系统的维护费用。Java对对象技术的全面支持和Java平台内嵌的API能缩短应用系统的开发时间并降低成本。Java的编译一次，到处可运行的特性使得它能够提供一个随处可用的开放结构和在多平台之间传递信息的低成本方式。特别是Java企业应用编程接口（Java Enterprise APIs）为企业计算及电子商务应用系统提供了有关技术和丰富的类库。

主要服务
--------

JDBC（Java Database Connectivity）提供连接各种关系数据库的统一接口，作为数据源，可以为多种关系数据库提供统一访问，它由一组用Java语言编写的类和接口组成。JDBC为工具/数据库开发人员提供了一个标准的API，据此可以构建更高级的工具和接口，使数据库开发人员能够用纯Java API 编写数据库应用程序，同时，JDBC也是个商标名。

EJB(Enterprise JavaBeans）使得开发者方便地创建、部署和管理跨平台的基于组件的企业应用。

Java RMI(Java Remote Method Invocation）用来开发分布式Java应用程序。一个Java对象的方法能被远程Java虚拟机调用。这样，远程方法激活可以发生在对等的两端，也可以发生在客户端和服务器之间，只要双方的应用程序都是用Java写的。

Java IDL(Java Interface Definition Language) 提供与CORBA(Common Object Request Broker 
Architecture）的无缝的互操作性。这使得Java能集成异构的商务信息资源。

JNDI(Java Naming and Directory Interface）提供从Java平台到的统一的无缝的连接。这个接口屏蔽了企业网络所使用的各种命名和目录服务。

JMAPI(Java Management API）为异构网络上系统、网络和服务管理的开发提供一整套丰富的对象和方法。

JMS(Java Message Service）提供企业消息服务，如可靠的消息队列、发布和订阅通信、以及有关推拉（Push/Pull）技术的各个方面。

JTS(Java transaction Service）提供存取事务处理资源的开放标准，这些事务处理资源包括事务处理应用程序、事务处理管理及监控。

JMF(Java Media Framework API），她可以帮助开发者把音频、视频和其他一些基于时间的媒体放到Java应用程序或applet小程序中去，为多媒体开发者提供了捕捉、回放、编解码等工具，是一个弹性的、跨平台的多媒体解决方案。

Annotation(Java Annotation），在已经发布的JDK1.5(tiger）中增加新的特色叫Annotation。Annotation提供一种机制，将程序的元素如：类，方法，属性，参数，本地变量，包和元数据联系起来。这样编译器可以将元数据存储在Class文件中。这样虚拟机和其它对象可以根据这些元数据来决定如何使用这些程序元素或改变它们的行为。
在Java技术中，值得关注的还有JavaBeans，它是一个开放的标准的组件体系结构，它独立于平台，但使用Java语言。一个JavaBean是一个满足JavaBeans规范的Java类，通常定义了一个现实世界的事物或概念。一个JavaBean的主要特征包括属性、方法和事件。通常，在一个支持JavaBeans规范的开发环境（如Sun Java Studio 和IBM VisualAge for Java）中，可以可视地操作JavaBean，也可以使用JavaBean构造出新的JavaBean。JavaBean的优势还在于Java带来的可移植性。EJB (Enterprise JavaBeans) 将JavaBean概念扩展到Java服务端组件体系结构，这个模型支持多层的分布式对象应用。除了JavaBeans，典型的组件体系结构还有DCOM和CORBA，关于这些组件体系结构的深入讨论超出了本书的范围。
JavaFX　Sun刚刚发布了JavaFX技术的正式版，它使您能利用JavaFX 编程语言开发富互联网应用程序（RIA）。JavaFX Script编程语言（以下称为JavaFX）是Sun微系统公司开发的一种declarative,staticallytyped（声明性的、静态类型）脚本语言。JavaFX技术有着良好的前景，包括可以直接调用Java API的能力。因为JavaFXScript是静态类型，它同样具有结构化代码、重用性和封装性，如包、类、继承和单独编译和发布单元，这些特性使得使用Java技术创建和管理大型程序变为可能。
JavaFX从它2007年发布以来，表现一直差强人意。Oracle收购了Sun之后，在JavaFX中投入了大量的精力进行推广和更新。JavaFX比较出名的应用应该是在2010年温哥华冬奥会上，调整了JavaFX中的很多概念，以及重新设计和实现了很多重要组件之后，得到的就是现在的JavaFX 2.0。JavaFX 2.0的beta版已经发布，正式版则定于2010年第3季度发布。JavaFX 2.0的新特性使得开发人员应该需要重新审视它在RIA开发领域中的位置。在很多情况下，JavaFX 2.0也会是不错的选择。

JMX（Java Management Extensions，即Java管理扩展）是一个为应用程序、设备、系统等植入
管理功能的框架。JMX可以跨越一系列异构操作系统平台、系统体系结构和网络传输协议，灵活的开发无缝集成的系统、网络和服务管理应用。

JPA(Java Persistence API),JPA通过JDK 5.0注解或XML（标准通用标记语言的子集）描述对象－关系表的映射关系，并将运行期的实体对象持久化到数据库中。

JSP（Java Server Pages)是由Sun Microsystems公司倡导、许多公司参与一起建立的一种动态网页技术标准。JSP技术有点类似ASP技术，它是在传统的网页HTML文件(*.htm,*.html)中插入Java程序段(Scriptlet)和JSP标记(tag)，从而形成JSP文件(*.jsp)。 用JSP开发的Web应用是跨平台的，既能在Linux下运行，也能在其他操作系统上运行。
