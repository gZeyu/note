1. `save`不会立刻提交到数据库，`flush`则会立刻提交生效
2. 总结一下统一异常处理的方法:

-   不使用随意返回各种数据类型, 要统一返回值规范.
-   不在业务代码中捕获任何异常, 全部交由  `@ControllerAdvice`  来处理.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc2Mjg5NTY3NSwtOTIxNzI2MDAyXX0=
-->