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
3. `OncePerRequestFilter`
在servlet-2.3中，Filter会过滤一切请求，包括服务器内部使用forward转发请求和<%@ include file="/index.jsp"%>的情况；到了servlet-2.4中Filter默认下只拦截外部提交的请求，forward和include这些内部转发都不会被过滤，但是有时候我们需要 forward的时候也用到Filter。
4. 要保证`CustomizedAuthFilterInvocationSecurityMetadataSource` 的权限数据的一致性
	- 每次读取权限数据前先调用`loadResourceDefine()`从`Mysql`刷新权限数据，缺点是效率不高
	- 使用`redis`做缓存
	- 数据更新标志位
	- 将权限数据做成线程安全的


## 杂项
1. `JpaRepository`配合`Optional`使用以简化代码
2. `HTTP`参数的表单和`JSON`区别
3. `bcrypt`算法将`salt`随机并混入最终加密后的密码，验证时也无需单独提供之前的`salt`，从而无需单独处理`salt`问题
4. `JWT`是自我校验的，所以是无状态的，服务器无需存储，但是是没办法做到主动注销（可以通过将`token`存`redis`里解决）
jwt实质就是一种TOKEN，那它与普通token有什么区别呢：  
- 普通token: 需要在服务端存储token跟用户的对应关系，每次请求都需要对token查询(对应关系)进行验证。  
- jwt: 把用户标识信息(如用户ID或其它标识)存储到jwt中(即与用户的对应关系存储在jwt中); 后端不需要存储jwt与用户的对应关系,而是从jwt中直接取得用户标识; 后端只需要对jwt的签名进行验证即可信任。  
总结为：普通token需要后端存储与用户的对应关系，而jwt自身携带对应关系。在大型的多系统中，普通token每次请求需要向用户资源服务器获取对应用户信息同时验证token，而jwt只需要验证签名有效即可信任且jwt自带用户信息, 无需额外请求。
- 单例模式
## 问题
1. `token`放`body`还是`header`？


<!--stackedit_data:
eyJoaXN0b3J5IjpbMjAzNzk3OTIzNCwxNTcxODAyOTk4LDM0Mz
E3ODgxMSwtMTQzNzcyMTYwMSwtMTg1NTM0NDAyLC05NTUwODU4
NTIsLTE2NzYwNzY2NzgsLTE3MDQxMjIwMSwtNzU4ODU0NDg3LC
0xNjI5NzIyNzY4LDIwNDQ1OTE4MDYsLTEyMjQyMjA2MTYsLTEz
NTIyMDc0NzgsLTE1OTQyNDkwODEsLTY2MTAxMzc4OSw3NDczMD
YyODksMzMzOTY3ODcsODQyOTg1OTI0LDE3ODk2MzI3NjAsMTE0
OTAzMjk4Ml19
-->