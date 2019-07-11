1. 需要取消`Spring Boot`的自动注入`Filter`
```java
@Bean  
public FilterRegistrationBean<CustomFilter> registration(CustomFilter filter) {  
  FilterRegistrationBean<CustomFilter> registration =  
      new FilterRegistrationBean<>(filter);  
  registration.setEnabled(false);  
  return registration;  
}
```
2. 替换security原有的登录过滤器时，需要关掉`formLogin`，否则`UsernamePasswordAuthenticationFilter`还是会被注册到`FilterChain`
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTgzMzI4NDI5LC01MjM4OTc1NzYsLTk3NT
c0OTA0MF19
-->