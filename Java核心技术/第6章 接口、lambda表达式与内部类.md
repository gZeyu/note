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
- 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkzMjcwMjg4MCwtMjU5ODA0MzQsLTI3NT
E2MTU5NiwtMTM5NTM3MTkwNSw1NjU3NjU1MTZdfQ==
-->