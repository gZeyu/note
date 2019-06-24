## xmodmap 
键盘映射
1. 将下面命令加入`~/.bashrc`或`~/.zshrc`文件中
```bash
if [ -f ~/.Xmodmap ]; then xmodmap ~/.Xmodmap; fi
```
2. 设置`~/.Xmodmap`
```bash
! 把F12键更换为Insert
keycode 96 = 118
! 把Insert键更换为F12
keycode 118 = 96
```
  currentnote## xev
查看按键`keycode`
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTIzNDIxMjI2MywtODgxMjM4MDg0XX0=
-->