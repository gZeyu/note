## TODO
 - [x] `Spring boot` 通用基类
 - [ ] `Spring boot` 统一异常处理 
 - [ ] `SpringAOP` + `log4J` + 注解的 日志管理
## 注意
1. 不要捕获任何异常
不要在**业务代码中**进行捕获异常, 即 `dao`、`service`、`controller` 层的所以异常都全部抛出到上层. 这样不会导致业务代码中的一堆  `try-catch`  会混乱业务代码.
2.  查询不到结果，返回Null还是抛出异常？
- 如果返回null是一个正常行为，则返回null。但在命名时最好给用户以提示，例如GetUserOrNull(string userName, string password)这样的函数名。
- 如果是错误，则抛出Exception。


## 杂项
1. `JpaRepository`配合`Optional`使用，简化代码

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NTQ2NDA5ODIsMzMzOTY3ODcsODQyOT
g1OTI0LDE3ODk2MzI3NjAsMTE0OTAzMjk4Ml19
-->