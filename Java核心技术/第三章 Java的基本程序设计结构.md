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
- **float**数值有个后缀**F**或**f**(如**3.14F**)
- **double**数值有个后缀**D**或**d**(如**3.14D**)
- 特殊浮点数值
	- 正无穷大：用一个正数除以0将得到一个正无穷大，通过Double或Float的POSITIVE_INFINITY表示
	- 负无穷大：用一个负数除以0将得到一个负无穷大，通过Double或Float的NEGATIVE_INFINITY表示、
	- 非数：0.0除以0.0或对一个负数开放将得到一个非数，通过Double或Float的NaN表示
- 所有非数值都被**Java**认为不相等，判断非数值可以使用**Double.isNaN 或 Float.isNaN**方法
### 3.3.3 char 类型
- **Unicode**转义序列会在解析代码之前被处理
``` java
/* 1. 下面两个字符串等价 */
 "\u0022+\u0022" 
 ""+""
/* 2. \u00A0会被替换成换行符，从而导致语法错误 */
// \u00A0 is a new line
/* 3. /u后面未跟着4个十六进制数 */
// Look inside c:/users
```
### 3.3.4 Unicode 和 char 类型
- 强烈建议不要在程序中使用**char**类型
### 3.3.5 **boolean 类型**
- 整型值与布尔值不能进行相互转换
## 3.4 变量
- 变量名必须是一个以字母开头并由字母或数字构成的序列，字母为任何表示字母的 **Unicode** 字符
- 使用 **Character** 类的 **isJavaldentifierStart** 和 **isJavaldentifierPart** 方法判断 **Unicode** 字符是否属于 **Java** 中的 “ 字母 ” 
- 不要在代码中使用 **$**，会与 **Java** 编译器或其他工具冲突
### 3.4.1 变量初始化
- 提倡逐一声明每一个变量
- 变量声明尽可能靠近变量第一次使用的地方
- **Java** 不区分变量的声明与定义
### 3.4.2 常量
- 常量名习惯上大写
- **const** 是 **Java** 的关键字，但目前并没有被使用
## 3.5 运算符
- 整数被0除会得到异常；浮点数被0除会得到无穷大或 **NaN**
- 使用 **strictfp** 关键字标记的方法必须使用严格的浮点计算。
### 3.5.1 数学函数与常量
- **StrictMath** 类可以确保在所有平台上得到相同的计算结果，**Math** 类不能
### 3.5.2 数值类型之间的转换
- **int** 和 **long** 转换为 **float** 和 **double** 可能有精度损失
### 3.5.3 强制类型转换
- 想达到布尔类型转数值类型的效果，可以使用条件表达式：
``` java
b?1:0
```
### 3.5.4 结合赋值和运算符
- 二元运算符得到一个类型与左侧操作数类型不同的值，将发送强制类型转换
``` java
// 两者等价
x += 3.5;
x = (int)(x + 3.5)
```
### 3.5.5 自增与自减运算符
- 自增与自减运算符的操作数不能是数值，故**4++** 不是合法的语句
### 3.5.6 关系和 **boolean** 运算符
- 短路
### 3.5.7 位运算符
- **>>>** 会使用0填充高位，而 **>>** 使用符号位填充高位
- 不存在 **<<<**
### 3.5.8 括号与优先级
- 注意右结合运算符
``` java
// 两者等价
a += b += c;
a += (b += c);
```
### 3.5.9 枚举类型
- 枚举类型的变量只能存储这个类型声明给定的枚举值或 **null** 值
## 3.6 字符串
- **Java** 字符串就是 **Unicode** 字符序列
- **Java** 没有内置的字符串类型，而是在标准 **Java** 类库中提供了一个预定义类 **String**
### 3.6.1 子串
### 3.6.2 拼接
- 当将一个字符串与一个非字符串的值进行拼接，后者被转换成字符串
### 3.6.3 不可变字符串
- **String** 类对象被称为不可变字符串
- 不可变字符串的优点：编译器可以让字符串共享
### 3.6.4 检测字符串是否相等
- 不要使用 **==** 运算符检测字符串是否相等
### 3.6.5 空串与 **Null** 串
- 检查一个字符串既不是空串也不是 **null**
``` java
if (str != null && str.length() != 0) // 正确
if (str.length() != 0 && str != null) // str为null时会出现错误
```
### 3.6.6 码点与代码单元
- 码点是指一个编码表中的某个字符对应的代码值
- **Unicode** 的码点分为17个代码级别，第一个级别是基本的多语言级别，码点从 **U+0000——U+FFFF**，其余的16个级别从 **U+10000——U+10FFFF** ，其中包括一些辅助字符
- 基本的多语言级别，每个字符用16位表示代码单元，而辅助字符采用连续的一对连续代码单元进行编码
``` java
String greeting = "Hello ";  
int n = greeting.length(); // 获取代码单元长度  
int cpCount = greeting.codePointCount(0, greeting.length()); // 获取码点数量  
char c = greeting.charAt(i); // 获取第i个代码单元  
int index = greeting.offsetByCodePoints(0, i);  // 获取第i个码点  
int cp = greeting.codePointAt(index);
```
### 3.6.7 **String API**
- **String** 类包含50多个方法
### 3.6.8 阅读联机 **API** 文档
### 3.6.9 构建字符串
- 使用 **StringBuilder** 类提高字符串拼接效率
## 3.7 输入输出
### 3.7.1 读取输入
- 由于输入是可见的，故**Scanner** 类不适用于从控制台读取密码，**Console** 类适用
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzE5NjA1ODU2LC0xNjQ3MjkwODM3LC0xOD
M4NTc0NjcxLDE5Mjg5NDYwNDEsLTIwODk0NzEyOTQsLTEzODYz
MjUyMzcsMjEwNTEyMDM1OSwtMjAzNDExMTg1NywtMTQ4NjI1MT
E5LC0xOTA2NzgzNzg1LC02NTQxNTkyMTAsLTExODcyMTg4OTUs
LTk5MzIyOTAxNywxODUxNjY4MDYyLC04NjIzODkwMDgsLTEyNT
E1NDI5MDhdfQ==
-->