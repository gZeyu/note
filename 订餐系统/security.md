1. 因为`Spring Security`只提供表单登录，需要实现`UsernamePasswordAuthenticationFilter`或`AbstractAuthenticationProcessingFilter`的子类，重写它的 `attemptAuthentication`方法，来自定义接口，字段实现登录
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjA2MTUzMTJdfQ==
-->