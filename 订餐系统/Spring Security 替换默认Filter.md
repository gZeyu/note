```ja
@Bean  
public FilterRegistrationBean<CustomIdentityPasswordAuthenticationFilter> registration(  
    CustomIdentityPasswordAuthenticationFilter filter) {  
  FilterRegistrationBean<CustomIdentityPasswordAuthenticationFilter> registration =  
      new FilterRegistrationBean<>(filter);  
  registration.setEnabled(false);  
  return registration;  
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzNzQ3NTg5MDZdfQ==
-->