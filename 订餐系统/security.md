## Knowledge
1. UserDetailsService
`UserDetailsService接口用于返回用户相关数据。它有loadUserByUsername()方法，根据username查询用户实体，可以实现该接口覆盖该方法，实现自定义获取用户过程。该接口实现类被DaoAuthenticationProvider 类使用，用于认证过程中载入用户信息。
--------------------- 
作者：neweastsun 
来源：CSDN 
原文：https://blog.csdn.net/neweastsun/article/details/79360724 
版权声明：本文为博主原创文章，转载请附上博文链接！
## Note
1. 因为`Spring Security`只提供表单登录，为了构建接受`JSON`参数的`REST API`登录接口，需要实现`UsernamePasswordAuthenticationFilter`或`AbstractAuthenticationProcessingFilter`的子类，重写它的 `attemptAuthentication`方法
2. 实现`UserDetailsService`接口并重写`loadUserByUsername`


<!--stackedit_data:
eyJoaXN0b3J5IjpbOTE0NTMxMjEyLC0xODI5ODcxNjgsLTY5OD
k1Mjg0Niw2MDYxNTMxMl19
-->