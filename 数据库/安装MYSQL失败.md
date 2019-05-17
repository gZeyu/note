
sudo rm /var/lib/mysql/ -R
 
sudo rm /etc/mysql/ -R
 
 
sudo apt-get autoremove mysql* --purge
 
sudo apt-get remove apparmor
 
 
sudo apt-get install mysql-server mysql-common
--------------------- 
作者：醉雨轩Y 
来源：CSDN 
原文：
版权声明：本文为博主原创文章，转载请附上博文链接！
<!--stackedit_data:
eyJoaXN0b3J5IjpbODAzOTE3MDc0XX0=
-->