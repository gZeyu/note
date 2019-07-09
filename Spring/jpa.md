1. `save`不会立刻提交到数据库，`flush`则会立刻提交生效
2. 使用`save`进行更新操作，如果提交的数据和原数据一致，`@LastModifiedDate`注解过的字段不会自动更新
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc4NDk1MzkxNSwtOTIxNzI2MDAyXX0=
-->