# Spring Initializr
有许多方法可以创建Spring Boot应用程序。最简单的方法是在[https://start.spring.io/](https://start.spring.io/)上使用Spring Initializr，这是一个在线Spring Boot应用程序生成器，或者通过IntelliJ IDEA的Spring Initializr选项生成SpringBoot项目。
# mybatis-spring-boot-starter
[http://www.mybatis.org/spring-boot-starter/mybatis-spring-boot-autoconfigure/index.html](http://www.mybatis.org/spring-boot-starter/mybatis-spring-boot-autoconfigure/index.html)
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

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE3NzEyNTM0MSwxNDg0NTUxNDQsMjA4MD
UwNTQyNiwtMTA1MDA3Mzc1MCw3MDExMDM0NDEsNzM1MjkxNjE3
LDMyMTgzMjE1NCwtMTM4MDIyOTQ2NiwxMzA2ODcwMzg1LDE0ND
Q0MzE0NjIsNTkzMDM3MDE5LDYxNTA4Nzg4NV19
-->