# Ubuntu18.04重置MySQL5.7的root密码
## debian-sys-maint
Debian/Ubuntu系统下mysql会有一个默认的**debian-sys-maint**账户,这个账户的密码随着mysql的安装和重启而生成。**debian-sys-maint**账户可以理解为通过系统的某个“非常规”程序对Mysql进行备份恢复等行为时，改程序所使用的登录MySQL的账户。
## 查看debian-sys-maint密码
```
sudo cat /etc/mysql/debian.cnf
```
## 使用debian-sys-maint账户


<!--stackedit_data:
eyJoaXN0b3J5IjpbODIxNzI0NTY1XX0=
-->