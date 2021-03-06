# Spring Initializr
有wo
# mybatis-spring-boot-starter
[http://www.mybatis.org/spring-boot-starter/mybatis-spring-boot-autoconfigure/index.html](http://www.mybatis.org/spring-boot-starter/mybatis-spring-boot-autoconfigure/index.html)
# springboot下使用mybatis
[https://www.jianshu.com/p/13616babe6ae](https://www.jianshu.com/p/13616babe6ae)
# model与entity（实体类）的区别
[https://blog.csdn.net/qq_38977097/article/details/81702349](https://blog.csdn.net/qq_38977097/article/details/81702349)
1. entity字段必须和数据库字段一样
2. model前端需要什么我们就给什么
3. domain很少用，代表一个对象模块
# 分层思想
[https://www.cnblogs.com/lkboy/p/4210742.html](https://www.cnblogs.com/lkboy/p/4210742.html)
# service和serviceImpl的选择
[https://www.cnblogs.com/zqsky/p/6143319.html](https://www.cnblogs.com/zqsky/p/6143319.html)
# Spring Boot 应用中server.context-path的作用
[https://blog.csdn.net/onedaycbfly/article/details/80108129](https://blog.csdn.net/onedaycbfly/article/details/80108129)
[https://www.baeldung.com/spring-boot-context-path](https://www.baeldung.com/spring-boot-context-path)
# map-underscore-to-camel-case
[https://blog.csdn.net/zhao0416/article/details/78427191](https://blog.csdn.net/zhao0416/article/details/78427191)
mybatis默认是属性名和数据库字段名一一对应的，即 
数据库表列：user_name 
实体类属性：user_name

但是java中一般使用驼峰命名 
数据库表列：user_name 
实体类属性：userName

在Springboot中，可以通过设置map-underscore-to-camel-case属性为true来开启驼峰功能。 
mybatis提供了一个配置：

## 开启驼峰命名转换

    mybatis.configuration.map-underscore-to-camel-case=true

使用该配置可以让mybatis自动将SQL中查出来的带下划线的字段，转换为驼峰标志，再去匹配类中的属性。
[https://www.cnblogs.com/flying607/p/8473075.html](https://www.cnblogs.com/flying607/p/8473075.html)
# 从源码角度理解Mybatis字段映射-驼峰式命名
[https://segmentfault.com/a/1190000010240142](https://segmentfault.com/a/1190000010240142)
# 关于springboot配置DataSource
[https://www.cnblogs.com/toughzcf/p/9835867.html](https://www.cnblogs.com/toughzcf/p/9835867.html)
# Spring Boot 官方属性
[https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#appendix](https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#appendix)
# Spring Boot 参考指南（Spring Boot文档）
[https://segmentfault.com/a/1190000015040758](https://segmentfault.com/a/1190000015040758)
# spring.datasource.url
app.datasource.url=jdbc:mysql://ip:port/DatabaseName 
# @Controller和@RestController的区别？
[https://www.cnblogs.com/shuaifing/p/8119664.html](https://www.cnblogs.com/shuaifing/p/8119664.html)
[https://www.jdon.com/50892](https://www.jdon.com/50892)
# @Resource注解
[https://www.cnblogs.com/loveweiwei/p/3901387.html](https://www.cnblogs.com/loveweiwei/p/3901387.html)

# Mybatis
[https://www.jianshu.com/p/25db002b0367](https://www.jianshu.com/p/25db002b0367)
# Mybatis自动创建表/更新表结构/动态建表
[https://blog.csdn.net/sun5769675/article/details/51757867](https://blog.csdn.net/sun5769675/article/details/51757867)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTgxMTMwMzE0OSwtMjA1OTY5MzMwOSwtOD
E0Mjk3MDUxLDE0ODEzNDU1NDgsMTA1MTE0MjIxMSwxOTAxMDI1
NTY2LDQ2OTc0NTE4LC02MDQ3NTgwMDQsMTUxNDQzMjM5LDExNz
cxMjUzNDEsMTQ4NDU1MTQ0LDIwODA1MDU0MjYsLTEwNTAwNzM3
NTAsNzAxMTAzNDQxLDczNTI5MTYxNywzMjE4MzIxNTQsLTEzOD
AyMjk0NjYsMTMwNjg3MDM4NSwxNDQ0NDMxNDYyLDU5MzAzNzAx
OV19
-->