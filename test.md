# 关于一个Web项目中数据校验的约定

1. 在controller中进行简单的数据校验,并且只对第一层级的参数进行校验,如传递一个username判断是否为空,但是传递的如果为user对象,则只判断user对象是否为空即可

2. 在service中对于直接传递进来的参数不再进行校验,如传递进来username字符串,user对象不校验,默认为合法,但在注释中写清楚相应的规则,使调用者清楚何时才可以调用此方法,对于多层级的参数则一边进行数据处理一边校验,如user.username等

3. 关于校验发现不正确的参数处理方式:  
    3.1 按照划分好的返回代码code自定义对应的exception,最好一个code值对应一个exception,便于阅读  
    3.2 在校验中发现不合理的参数,抛出相应的exception,设置好其中的message  
    3.3 注册一个或多个ExceptionHandler,其中接住抛出异常,进行统一的处理,转换为更友好的方式传递给前端
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTY2NjIzNjIzXX0=
-->