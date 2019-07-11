但是在一些特定的场景会有一些特定的需求，我们可能需要自己实现注册，但是又需要Filter实例存在于Spring容器中，以便让其使用到Spring提供的众多服务(自动注入其他组件……)。所以需要取消Spring Boot的自动注入Filter。
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
eyJoaXN0b3J5IjpbMTU4Mjk4NDA2NywtOTc1NzQ5MDQwXX0=
-->