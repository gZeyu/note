# Ubuntu18.04重置MySQL5.7的root密码
## debian-sys-maint
Debian/Ubuntu系统下mysql会有一个默认的**debian-sys-maint**账户,这个账户的密码随着mysql的安装和重启而生成。**debian-sys-maint**账户可以理解为通过系统的某个“非常规”程序对Mysql进行备份恢复等行为时，改程序所使用的登录MySQL的账户。
## 查看debian-sys-maint密码
``` bash
sudo cat /etc/mysql/debian.cnf
```
## 登录MySQL
``` bash
mysql -udebian-sys-maint -p{password}
```
## 重置root密码
``` bash
mysql> use mysql; 
mysql> update user set authentication_string=PASSWORD("{new password}") where User='root'; # 更改密码 
mysql> update user set plugin="mysql_native_password"; 
mysql> flush privileges; 
mysql> quit;
```
 ### 参考
>[1] :  [https://blog.csdn.net/wei_love_2017/article/details/82313444](https://blog.csdn.net/wei_love_2017/article/details/82313444)

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTM2ODM5ODU3OF19
-->