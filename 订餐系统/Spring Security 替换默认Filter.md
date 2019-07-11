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
2. 替换security原有的登录过滤器时，需要关掉`formLogin`，
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjEwNjUyNTgxMCwtNTIzODk3NTc2LC05Nz
U3NDkwNDBdfQ==
-->