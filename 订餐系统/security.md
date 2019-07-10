1. 因为`Spring Security`只提供表单登录，所以需要实现`UsernamePasswordAuthenticationFilter`或`AbstractAuthenticationProcessingFilter`的子类，重写它的 `attemptAuthentication`方法，来构建`REST API`登录接口
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMDA5ODA0LC02OTg5NTI4NDYsNjA2MT
UzMTJdfQ==
-->