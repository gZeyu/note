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

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTA3OTE4ODgwNiwtOTc1NzQ5MDQwXX0=
-->