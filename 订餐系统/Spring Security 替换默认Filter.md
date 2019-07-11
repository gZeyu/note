```java
@Bean  
public FilterRegistrationBean<CustomIdentityPasswordAuthenticationFilter> registration(  
    CustomFilter filter) {  
  FilterRegistrationBean<CustomFilter> registration =  
      new FilterRegistrationBean<>(filter);  
  registration.setEnabled(false);  
  return registration;  
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTkzMjk0NDE3XX0=
-->