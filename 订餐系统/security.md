## Knowledge
1. `UserDetailsService`
`UserDetailsService`接口用于返回用户相关数据。它有`loadUserByUsername()`方法，根据`username`查询用户实体，可以实现该接口覆盖该方法，实现自定义获取用户过程。该接口实现类被`DaoAuthenticationProvider `类使用，用于认证过程中载入用户信息。
## Note
1. 因为`Spring Security`只提供表单登录，为了构建接受`JSON`参数的`REST API`登录接口，需要实现`UsernamePasswordAuthenticationFilter`或`AbstractAuthenticationProcessingFilter`的子类，重写它的 `attemptAuthentication`方法
2. 实现`UserDetailsService`接口并重写`loadUserByUsername`，达到自定义获取用户实体的目的
2. 对于系统的filter`的默认顺序，是在一个`FilterComparator`类中确定的
### 涉及到登录流程接口、类及函数
1. `UsernamePasswordAuthenticationFilter.attemptAuthentication()`负责解析`HttpServletRequest`提取登录参数并生成`UsernamePasswordAuthenticationToken`
2. `UserDetailsService.loadUserByUsername`负责生成`UserDetails`
3. `DaoAuthenticationProvider.authenticate()`验证`Authentication`和`UserDetails`是否匹配
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk1NTM1NDg5LC0xNTYzMjQzNzcyLDEzMz
k4MDc3MTcsMTcxMTY4MDAzLC04MjgxMDg4NTYsNDQwNDQyODYw
LC0xNjgyMDA1NTAwLDEwMzg3Mzg1NjgsLTE4Mjk4NzE2OCwtNj
k4OTUyODQ2LDYwNjE1MzEyXX0=
-->