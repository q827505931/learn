###  											java基础

###### 1.JDK 和 JRE的区别

​	JDK java development kit java 开发工具包，包括了Java RunTime Environment java 运行时环境以及一些编译开发工具，

​	JRE Java RunTime Environment java 运行时环境，只包含了java运行时所需环境

​	简单来讲 如果只需要运行java程序，那么只需要JRE就够了，如果想要开发调试，必须有JDK工具

###### 2.== 和equals 

​	对于基本数据类型和引用数据类型 == 含义不同 

​		基本数据类型的 == 比较的是值是否相同

​		引用数据类型的 == 比较的是引用是否相同

​	基本数据类型无equals 操作

​		引用数据类型的equals默认比较的是引用是否相同，只是有些方法重写了equals方法，变成了值比较

###### 3.hashcode相同,equals一定相等吗

​		并不一定，hash值相同并不一定equals

###### 4.final 作用

​		final 修饰类代表类不可被继承 修饰方法代表方法不可被重写 修饰变量表示该变量为常量，必须初始化，一旦赋值不可改变 

###### 5.几个Math 函数

​		Math.round(-0.5) 数轴向右取整 0

​		Math.ceil(-0.5)数轴向右取整 为double -0.0 有正负号的区别

​		Math. floor(-0.5)向左取整 为-1.0

###### 6.基本数据类型

​		四类八种 数值型 byte 1 short 2 int 4 long 8

​						字符型 char 4

​						浮点型 float 4 double 8

​						boolean型

###### 7.操作字符串的类

​		String, StringBuilder, StringBuffer

​		String 每次操作都会新建一个String对象，并将引用指向新对象，效率较低，触发大量gc 一直在变化的字符串建议使用后两种

​		后两种都是基于带缓冲区的字符串操作类，每次操作会在当前对象后面追加字符，效率更高，扩容方式为2倍+2 区别在于前者线程不安全 但相对效率更高 后者线程安全 效率较低 根据具体情况选择

###### 8.String str = "i" 与String str = new String("i") 区别

前者是在常量池中创建一个i,并将str引用指向常量池中的i 

后者是在堆内存中创建一个对象，并将str引用指向堆内存中的对象

###### 9.字符串反转

StringBuffer中的reverse 

###### 10.接口和抽象类的区别

首先 接口可以看做是一种对行为的规范 抽象是是对类的抽象

接口需要被实现 implements 可以多实现 抽象类需要被继承 extends 只能单继承

接口中的方法默认是public 修饰的 并且不能有方法体 不过jkd1.8之后可以有静态方法以及默认方法 可以写方法体了 抽象类的抽象方法可以是任意权限修饰符

抽象类可以有main方法 接口不可以有

###### 11.权限修饰符

private 只能在本类使用

default 默认 只能在本包下使用

protected 同包以及不同包的子类

public 所有类都能使用 最大的权限修饰符

###### 12.IO流

按输入输出分可以分为输入流和输出流

按操作的字节和字符区分可以分为字节流和字符流

按功能分 节点流和功能流

节点流：从数据源直接得到的流 

功能流：对节点流的增强 ，包装节点流（装饰者模式）

​			缓冲流：bufferedReader/Writer/inputStream/OutputStream 

​			转换流：inputStreamReader/Writer

​			对象流：ObjectInputStream/OutputStream 必须实现序列化接口 不想序列化的字段transient修饰

​			数据流：DataInputStream 基本数据流

###### 13.BIO ,NIO,AIO

BIO 传统的IO 阻塞式，模式简单，使用方便，并发性能低，每次都需要新建一个流读写，单向的

NIO 同步非阻塞式IO 基于通道（channel）和缓冲(buffer)，选择器(selector)，实现了多路复用 

AIO 异步非阻塞式IO 基于事件和回调机制（待补充）



