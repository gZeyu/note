1. 程序清单5-15未按原文编写
> P199，”**ObjectAnalyzer** 将记录已经被访问过的对象“
2.  Java有一个限制，无法构造泛型类型`T`的数组
> P237， 6.3.5

如果允许创建泛型数组，就绕过了泛型的编译时的类型检查
3.  
> P241

Java泛型仅针对引用类型，如果使用Function，会将代码中的int进行装箱，从而在性能上付出代价。java.util.function包针对基本类型的int、double和long提供支持，当输入或/和输出为基本类型时，可以避免自动装箱的操作。
4. **闭包（closure）**
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTcyMTYzMjcxNyw0NTkxNjMxNzgsLTk2Nz
cwNzE5NV19
-->