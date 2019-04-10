# 第6章 接口、lambda表达式与内部类
## 6.1 接口
### 6.1.1 接口概念
- **接口的所有方法自动地属于public**（在实现接口时，必须把方法声明为public）
- **接口绝不能含有实例域**（在Java SE 8之前，也不能在接口中实现方法）
### 6.1.2 接口的特性
- 不能使用new运算符实例化一个接口；可以声明接口变量，接口变量必须引用实现了接口的类对象
- 接口也可以被拓展
- 接口不能包含实例域或静态方法，但却可以包含常量
- 接口中的方法被自动设为public
- 接口中的域被自动设为public static final
### 6.1.3 接口与抽象类
### 6.1.4 静态方法
- 在Java SE 8中，允许在接口中增加静态方法
### 6.1.5 默认方法
- 可以为接口方法提供一个默认实现。必须用default修饰符标记这样一个方法
### 6.1.6 解决默认方法冲突
- 解决默认方法冲突
	1. 超类优先
	2. 接口冲突
- 千万不要让一个默认方法重新定义Object类中的某个方法
## 6.2 接口示例
### 6.2.1 接口与回调
### 6.2.2 Comparator接口
- Compare接口与Comparator接口
	1. 排序规则实现的方法不同
		- Comparable接口的方法：`compareTo(Object o)`
		- Comparator接口的方法：`compare(T o1, To2)`
	2. 类设计前后不同
	    - Comparable接口用于在类的设计中使用
	    - Comparator接口用于类设计已经完成，还想排序（Arrays）
### 6.2.3 对象克隆
- 默认的克隆操作是“浅拷贝”
## 6.3 lambda表达式
### 6.3.1 为什么引入lambda表达式
- 使用lambda表达式，会使得设计的代码会更加简洁，且具有可读性
### 6.3.2 lambda表达式的语法
- **即使lambda表达式没有参数，仍然要提供空括号**
- **如果可以推导出一个lambda表达式的参数类型，则可以忽略其类型**
- **如果方法只有一个参数，而且这个参数的类型可以推导得出，那么甚至还可以省略小括号**
- **无需指定lambda表达式的返回类型**。如果一个lambda表达式只在某些分支返回一个值，而在另外一些分支不返回值，这是不合法的
### 6.3.3 函数式接口
- 函数式接口（functional interface）
	- 只有一个抽象方法
- lambda表达式可以转换为接口
### 6.3.4 方法引用
- 方法引用（method reference）
	- `object::instanceMethod`，等价于提供方法参数的lambda表达式
	- `Class::staticMethod`，等价于提供方法参数的lambda表达式
	- `Class::instanceMethod`，第一个参数会成为方法的目标
	- `this::instanceMethod`，可以在方法引用中使用`this`参数
	- `super::instanceMethod`，可以在方法引用中使用`super`参数
``` java
// 对于object::instanceMethod或Class::staticMethod
// 以下两种方式等价
System.out::println // 方法引用
x->System.out.println(x) // lambda表达式
```
``` java
// 对于Class::instanceMethod
// 以下两种方式等价
String::compareToIgnoreCase // 方法引用
(x, y)->x.compareToIgnoreCase(y) // lambda表达式
```
``` java
// 对于this::instanceMethod
// 以下两种方式等价
this::equals // 方法引用
x->this.equals(x) // lambda表达式
```
``` java
// 对于super::instanceMethod
// 以下两种方式等价
super::equals // 方法引用
x->super.equals(x) // lambda表达式
```
### 6.3.5 构造器引用
- 构造器引用
	- `Class::new`
- 可以用数组类型建立构造器引用
``` java
// 以下两种方式等价
int[]::new // 方法引用
x->new int[x] // lambda表达式
```
- Java有一个限制，无法构造泛型类型`T`的数组
### 6.3.6 变量作用域
- **闭包（closure）**
- lambda表达式可以捕获外围作用域中变量的值
- lambda表达式中捕获的变量必须实际上是**最终变量（effectively final）**
- 在lambda表达式中声明与一个局部变量同名的参数或局部变量是不合法的
- **在一个lambda表达式中使用`this`关键字时，是指创建这个lambda表达式的方法的`this`参数**
### 6.3.7 处理lambda表达式
- 延迟执行（deferred execution）
- 可以使用`@FunctionalInterface`注解来标注函数式接口
- Java泛型仅针对引用类型，如果使用Function，会将代码中的int进行装箱，从而在性能上付出代价。java.util.function包针对基本类型的int、double和long提供支持，当输入或/和输出为基本类型时，可以避免自动装箱的操作。
- **大多数标准函数式接口都提供了非抽象方法来生成或合并函数**
### 6.3.8 再谈Comparator
## 6.4 内部类
- **内部类（inner class）**
- 使用内部类的原因
	- 内部类方法可以访问该类定义所在的作用域中的数据，包括私有的数据
	- 内部类可以对同一个包中的其他类隐藏起来
	- 当想要定义一个回调函数而且不想编写大量代码时，使用匿名（anonymous）内部类比较便捷
### 6.4.1 使用内部类访问对象状态
- 内部类既可以访问自身的数据域，也可以访问创建它的外围类对象的数据域
- 外围类的引用在内部类构造器中设置，这个引用在内部类的定义中是不可见的
- 只有内部类可以是私有类，而常规类只可以具有包可见性，或共有可见性
### 6.4.1 内部类的特殊语法规则
- 使用外围类引用的正规语法
``` java
OuterClass.this
```
- 可以采用下列语法格式更加明确地编写内部对象的构造器
``` java
outerObject.new InnerClass(construction parameters)
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY5MzM0Mjk3MSwxMzI1MDM3NzE0LDQyOD
QxNjQzMCwtMTA2NTI5OTY5MSw2NjY0NzA1OCw2OTk3MzA3MzUs
LTIxMDY1OTY4NSwxMjIxNDg5MTkyLDE1Mjg2ODA5MTIsLTEwMz
g0ODA0NywtMTExNzEwOTk3NSwtMTc5ODMzNDMwMCwxNzA0MjQz
MTQ3LDExMDcwNTc5MjksMTQ1MDIzOTAyLDE0NTAyMzkwMiwxOD
c5NzY5NzMxLC05MTQzMTcxNDksLTY5MzM0MDgzMSwtMzM3Nzcx
MjA3XX0=
-->