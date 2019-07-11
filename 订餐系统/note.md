## TODO
 - [x] `Spring boot` 通用基类
 - [ ] `Spring boot` 统一异常处理 
 - [ ] `SpringAOP` + `log4J` + 注解的 日志管理
## 注意
1. 不要捕获任何异常
不要在**业务代码中**进行捕获异常, 即 `dao`、`service`、`controller` 层的所以异常都全部抛出到上层. 这样不会导致业务代码中的一堆  `try-catch`  会混乱业务代码.
2.  查询不到结果，返回`null`还是抛出异常？
- 如果返回`null`是一个正常行为，则返回`null`。但在命名时最好给用户以提示，例如`GetUserOrNull(string userName, string password)`这样的函数名。
- 如果是错误，则抛出`Exception`


## 杂项
1. `JpaRepository`配合`Optional`使用以简化代码
2. `HTTP`参数的表单和`JSON`区别
3. 使用`bcrypt`作为加密算法，jiemi



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2MjU0ODg3NywtNjYxMDEzNzg5LDc0Nz
MwNjI4OSwzMzM5Njc4Nyw4NDI5ODU5MjQsMTc4OTYzMjc2MCwx
MTQ5MDMyOTgyXX0=
-->