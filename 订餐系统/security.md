1. 因为`Spring Security`只提供表单登录，为了构建接受`JSON`参数的`REST API`登录接口，需要实现`UsernamePasswordAuthenticationFilter`或`AbstractAuthenticationProcessingFilter`的子类，重写它的 `attemptAuthentication`方法
2. 实现`UserDetailsService`
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMzNTI3MDUxMCwtMTgyOTg3MTY4LC02OT
g5NTI4NDYsNjA2MTUzMTJdfQ==
-->