# 第三章 Java的基本程序设计结构
## 3.1 一个简单的Java应用程序
- 关键字**public**，访问控制符( **access modifier** )
- 类名规则
	- 以字母开头，紧跟字母、数字的任意组合
	- 长度无限制
	- 不能使用保留字

> 在java规范中没有限制类名的长度，但是系统本身会限制。
> 1. java这个语言本身：没有限制。
> 2. java虚拟机本身的规范：在java虚拟机看来类名本生也是字符串，所以[Java虚拟机规范](https://www.baidu.com/s?wd=java%E8%99%9A%E6%8B%9F%E6%9C%BA%E8%A7%84%E8%8C%83&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)是限制为65535
> 3. 系统限制：
>  - Linux文件名的长度限制是255个字符
>  - windows下完全限定文件名必须少于260个字符，目录名必须小于248个字符
- 标准命名规范：
	- 类名大写
	- 驼峰命名法
- 源代码文件名必须与公共类名一致，且以**.java**作为扩展名
- **Java**大小写敏感
- **Java**虚拟机默认从指定类的**main**方法开始执行
- 类的源文件必须包含**main**方法
``` java
public class ClassName {
	public static void main(String[] args) {
		program statements
	}
}
```
- main方法
	- **Java SE 1.4**及以后**main**方法必须是**public**
	- 必须是静态(**static**)
	- 无返回值。如果**main**方法正常退出，那么**Java**应用程序退出代码为0。可调用**System.exit**终止程序返回其他代码
- **Java**通用调用语法
``` java
object.method(parameters)
```
## 3.2 注释
- 注释不会编译到可执行文件中
- 三种标记注释，第三种可以用来自动生成文档
``` java
// program statements
/* program statements */
//**
  * program statements
  * /
```
- /**/注释不能嵌套
## 3.3 数据类型
- 一共8种基本类型(**primitive type**)
	- 4种整型
	- 2种浮点类型
	- 1种用于表示**Unicode**编码的字符类型**char**
	- 1种表示布尔值的**boolean**类型
### 3.3.1 整型
| 类型 | 字节数 | 取值范围 | 默认值 |
|--|--|--|--|
| **int** | 4 | -2^31 ~ 2^31-1，-2 147 483 648 ~ 2 147 483 647(超过20亿) | **0** |
| **short** | 2 | -32 768 ~ 32 717 | **0** |
| **long** | 8 | -2^63 ~ 2^63-1，-9 223 372 036 854 775 808 ~ 9 223 372 036 854 775 807 | **0** |
| **byte** | 1 | -128 ~ 127 | **0L** |
- 长整型数值有个后缀**L**或**l**(如**40000000000L**)
- 十六进制有个前缀**0x**或**0X**(如**0xabcd**)
- 八进制有个前缀**0**(如**010**)
- **Java7**开始，二进制有个前缀**0b**或**0B**(如**ob1001**)
- **Java7**开始，可以为字面量加下划线(如**ob1001_1001_1001_1001或1_000_000**)
- **Java**没有无符号类型
### 3.3.2 浮点型
| 类型 | 字节数 | 取值范围 | 默认值 |
|--|--|--|--|
| **float** | 4 | ±3.402 823 47 E +38 F (有效位数为6 ~ 7位) | **0** |
| **double** | 8 | ± 1.797 693 134 862 315 70 E + 308(有效位数为15位) | **0** |
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk5MzIyOTAxNywxODUxNjY4MDYyLC04Nj
IzODkwMDgsLTEyNTE1NDI5MDhdfQ==
-->