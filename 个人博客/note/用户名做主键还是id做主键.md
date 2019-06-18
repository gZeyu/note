1. 一般来说，主键最好是无意义的字段
2. 用数字做索引查询和搜索的速度都比字符串快
3. 假如从用户表里删除了一个用户a，再增加用户b，用户b的用户名与用户a相同。如果用户a的权限表相对用户名没有清除干净，就会引发权限安全问题。
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTcwNjgzNTQ3MiwxOTQyNjM4MzgxXX0=
-->