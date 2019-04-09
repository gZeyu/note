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

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY5NjEzMDUzOCwtMzM3NzcxMjA3LC0xOT
c2Mjk0NzUyLDE5ODQ5OTAzMjEsODM1MTU5MTY0LC05MzI3MDI4
ODAsLTI1OTgwNDM0LC0yNzUxNjE1OTYsLTEzOTUzNzE5MDUsNT
Y1NzY1NTE2XX0=
-->