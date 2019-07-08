 - [ ] `Spring boot` 通用基类
 - [ ] `Spring boot` 统一异常处理 
 - [ ] `SpringAOP` + `log4J` + 注解的 日志管理
## 
1. 不要捕获任何异常
不要在**业务代码中**进行捕获异常, 即 `dao`、`service`、`controller` 层的所以异常都全部抛出到上层. 这样不会导致业务代码中的一堆  `try-catch`  会混乱业务代码.


### 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3NTg0OTg3NTMsMzMzOTY3ODcsODQyOT
g1OTI0LDE3ODk2MzI3NjAsMTE0OTAzMjk4Ml19
-->