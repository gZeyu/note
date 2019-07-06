## xmodmap 
键盘映射
1. 将下面命令加入`~/.bashrc`或`~/.zshrc`文件中
```bash
if [ -f ~/.Xmodmap ]; then xmodmap ~/.Xmodmap; fi
```
2. 设置`~/.Xmodmap`
```bash
! 把Insert键更换为F12
keycode 118 = F12 F12 F12 F12 F12 F12 XF86Switch_VT_12
! 把F12键更换为Insert
keycode 96 = Insert NoSymbol Insert

```
## xev
查看按键`keycode`

setkeycodes
？？？？
##
sudo gedit /lib/systemd/system/gdm3.service

把其中的

ExecStartPre=/usr/share/gdm/generate-config

更改为

ExecStartPre=/usr/bin/xinit /usr/share/gdm/generate-config

然后

sudo dpkg-reconfigure gdm3

重启后接hdmi线

reboot

成功～

转载于:https://www.cnblogs.com/clemente/p/10531777.html
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc0NzAxMzY3MSwtMjI2NTI1NjgsMTE3Mz
ExNjUzMyw4OTg4NjE3MDMsMTU5NTk0NTkxNywtODgxMjM4MDg0
XX0=
-->