1. 因为`Spring Security`只提供表单登录，需要实现`UsernamePasswordAuthenticationFilter`或`AbstractAuthenticationProcessingFilter`的子类，重写它的 `attemptAuthentication`方法，以自定义登录接口及登录字段
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwODA1ODEyODIsNjA2MTUzMTJdfQ==
-->