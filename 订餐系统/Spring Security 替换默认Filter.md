```java
@Bean  
public FilterRegistrationBean<CustomFilter> registration(  
    CustomFilter filter) {  
  FilterRegistrationBean<CustomFilter> registration =  
      new FilterRegistrationBean<>(filter);  
  registration.setEnabled(false);  
  return registration;  
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzODE5NjI3ODJdfQ==
-->