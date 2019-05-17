```bash
sudo rm /var/lib/mysql/ -R
sudo rm /etc/mysql/ -R
sudo apt-get autoremove mysql* --purge
sudo apt-get remove apparmor
sudo apt-get install mysql-server mysql-common
```
 ### 参考
>[1] :  [https://blog.csdn.net/miao0967020148/article/details/80218170 ](https://blog.csdn.net/miao0967020148/article/details/80218170)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwNTg2NDExMTFdfQ==
-->