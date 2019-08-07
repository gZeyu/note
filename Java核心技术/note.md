####  javac和java区别
cmd中，执行java命令与javac命令的区别：
javac：是编译命令，将java源文件编译成.class字节码文件。
例如：javac hello.java 
将生成hello.class文件
java：是运行字节码文件；由java虚拟机对字节码进行解释和运行。
#### jar
JAR包是Java中所特有一种压缩文档,其实大家就可以把它理解为.zip包。当然也是有区别的,JAR包中有一个META-INF\MANIFEST.MF文件,当你找成JAR包时,它会自动生成。
JAR包是由JDK的jar命令生成的。
####  为什么重写equals方法时必须重写hashcode方法
#### java 创建对象的几种不用方式
#### nextLine()与next()的区别就在于:next()函数不会接收回车符和tab
#### 使用getComponentType()来获取数组类型的子类型
#### 可变参数是兼容数组参数的，但是数组参数却无法兼容可变参数
#### 可变参数必须作为参数列表的最后一项，而不能放在定长参数的前面
#### 组件类型相同的可变参数方法与数组参数方法不能重载
#### LinkedHashMap实现LRU算法
#### HashMap的afterNodeAccess()、afterNodeInsertion()、afterNodeRemoval()方法都是空实现，留着LinkedHashMap去重写。LinkedHashMap靠重写这3个方法就完成了核心功能的实现。不得不感叹，HashMap和LinkedHashMap设计之妙。
#### Arrays . asList返回的对象不是 ArrayList 。 它是一个视图对象

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTcxMjE2NDg0OCwxNjkzNTE4NDAyLC0xMT
QzNDYxMDMwLDE3NjA5MjM3OTAsLTQxNDQ4NjA2NywtMTQxMTYy
NzQ2NCw2NjYzMDc3MjYsLTk4MTI5ODIyLC0xNzA4Mzg2OTk2XX
0=
-->