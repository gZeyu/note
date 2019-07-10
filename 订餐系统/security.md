1. 因为`Spring Security`只提供表单登录，为了构建接受`JSON``REST API`登录接口，需要实现`UsernamePasswordAuthenticationFilter`或`AbstractAuthenticationProcessingFilter`的子类，重写它的 `attemptAuthentication`方法
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI2MDE2NjEwLC02OTg5NTI4NDYsNjA2MT
UzMTJdfQ==
-->