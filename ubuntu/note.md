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

## inxi

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTgxNzMwNjg3NSwtNzQ3MDEzNjcxLC0yMj
Y1MjU2OCwxMTczMTE2NTMzLDg5ODg2MTcwMywxNTk1OTQ1OTE3
LC04ODEyMzgwODRdfQ==
-->