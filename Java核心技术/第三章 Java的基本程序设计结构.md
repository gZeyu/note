# 第三章 Java的基本程序设计结构
## 3.1 一个简单的Java应用程序
- 关键字**public**，访问控制符( **access modifier** )
- 类名规则
	- 以字母开头，紧跟字母、数字的任意组合
	- 长度无限制
	- 不能使用保留字

> 在java规范中没有限制类名的长度，但是系统本身会限制。
> 1. java这个语言本身：没有限制。
> 2. java虚拟机本身的规范：在java虚拟机看来类名本生也是字符串，所以[java虚拟机规范](https://www.baidu.com/s?wd=java%E8%99%9A%E6%8B%9F%E6%9C%BA%E8%A7%84%E8%8C%83&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)是限制为65535
> 3. 系统限制：
>  - Linux文件名的长度限制是255个字符
>  - windows下完全限定文件名必须少于260个字符，目录名必须小于248个字符
- 标准命名规范：
	- 类名大写
	- 驼峰命名法
- 源代码文件名必须与公共类名一致，且以**.java**作为扩展名

<!--stackedit_data:
eyJoaXN0b3J5IjpbNTYwNTkwMDA0XX0=
-->