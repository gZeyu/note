```bash
sudo rm /var/lib/mysql/ -R
sudo rm /etc/mysql/ -R
sudo apt-get autoremove mysql* --purge
sudo apt-get remove apparmor
sudo apt-get install mysql-server mysql-common
```

 ### 参考
>[1] : [https://blog.csdn.net/iehadoop/article/details/82961264](https://blog.csdn.net/iehadoop/article/details/82961264)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTUxNjAxNjk5OV19
-->