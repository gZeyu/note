#### 1. `<router-view></router-view>`的用法
可以这样理解，正常写法中，一层路径(`/xxx`)对应一个`router-view`。
比如url: `/a/b/c` (假设`a`、b、c都为正常路径，不会作为参数)
-   那`/a`对应的就是App.vue中的`router-view`，`/a`进入`a.vue`中
-   那`/a/b`对应的就是a.vue中的`router-view`，  `/a/b`进入`b.vue`中
以此类推。
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDUxNjY0NzIyXX0=
-->