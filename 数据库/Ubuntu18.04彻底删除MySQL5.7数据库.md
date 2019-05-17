``` bash
#查看MySQL的依赖项
dpkg --list|grep mysql
#卸载
sudo apt-get remove mysql-common
sudo apt-get autoremove --purge mysql-server-5.7
#清除残留数据
dpkg -l|grep ^rc|awk '{print$2}'|sudo xargs dpkg -P
#再次查看MySQL的剩余依赖项
dpkg --list|grep mysql
#继续删除剩余依赖项，
sudo apt-get autoremove --purge mysql-apt-config
```
>参考:[https://blog.csdn.net/iehadoop/article/details/82961264](https://blog.csdn.net/iehadoop/article/details/82961264)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ3NTA2MjAyOV19
-->