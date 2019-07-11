## TODO
 - [x] `Spring boot` 通用基类
 - [ ] `Spring boot` 统一异常处理 
 - [ ] `SpringAOP` + `log4J` + 注解的 日志管理
 - [ ] 访问不存在的`url`
 - [x] 加盐加密
 - [ ] 401与403区别
## 注意
1. 不要捕获任何异常
不要在**业务代码中**进行捕获异常, 即 `dao`、`service`、`controller` 层的所以异常都全部抛出到上层. 这样不会导致业务代码中的一堆  `try-catch`  会混乱业务代码.
2.  查询不到结果，返回`null`还是抛出异常？
- 如果返回`null`是一个正常行为，则返回`null`。但在命名时最好给用户以提示，例如`GetUserOrNull(string userName, string password)`这样的函数名。
- 如果是错误，则抛出`Exception`


## 杂项
1. `JpaRepository`配合`Optional`使用以简化代码
2. `HTTP`参数的表单和`JSON`区别
3. `bcrypt`算法将`salt`随机并混入最终加密后的密码，验证时也无需单独提供之前的`salt`，从而无需单独处理`salt`问题

<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA0NDU5MTgwNiwtMTIyNDIyMDYxNiwtMT
M1MjIwNzQ3OCwtMTU5NDI0OTA4MSwtNjYxMDEzNzg5LDc0NzMw
NjI4OSwzMzM5Njc4Nyw4NDI5ODU5MjQsMTc4OTYzMjc2MCwxMT
Q5MDMyOTgyXX0=
-->