## xmodmap 
键盘映射
1. 将下面命令加入`.bashrc`或`.zshrc`文件中
```bash
if [ -f ~/.Xmodmap ]; then xmodmap ~/.Xmodmap; fi
```
2. 设置
```
! 把esc键更换为Caps_Lock
keycode 9 = Caps_Lock NoSymbol Caps_Lock

!把Caps_Lock键更换为Shift_L
keycode 66 = Shift_L NoSymbol Shift_L

!把Shift_L键更换为Control_L键 
keycode 50 = Control_L NoSymbol Control_L
```
## xev
查看按键`keycode`
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjEyNDgyNzQ5XX0=
-->