1. 一般来说，主键最好是无意义的字段。
2. 用户名可以是千奇百怪的字符串，而用ID（一般用guid或自增int）是比较规则的字母数字序列。而用数字做索引查询和搜索的速度比字符串快。
3. 假如以用户名作为主键并与其他表关联，当删除用户后，再创建一个同名的用户，可能导致这些关联紊乱。而用绝对唯一的ID字段则不会。
4. 用户名以后可能要更改，而且以后可能有重复的用户名，所以用用户名作主键很不妥，而用ID字段来做主键可以完全避免这种情况。
5. 当百万数据时，如果修改主键，会导致数据库自动重建索引，所以修改操作会非常慢，甚至超时。
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2MjMyNDM4MzUsLTIwOTEyOTEwNDksMT
MyMDcxNDQ4OCwtNDgwODE2MTI5LDE5OTI3ODg4MiwxOTQyNjM4
MzgxXX0=
-->