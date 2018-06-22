### 环境
---
- Windows 7 64bit
### 当前目录下打开CMD
---
shift+右键 - 打开命令行窗口

### 以管理员身份在当前目录打开命令行窗口
---
- 新建一个注册表文件cmd.reg,保存好双击运行注册表文件注入，查看右键
```
Windows Registry Editor Version 5.00  
; Created by: Shawn Brink  
; http://www.sevenforums.com  
; Tutorial: http://www.sevenforums.com/tutorials/47415-open-command-window-here-administrator.html   
[-HKEY_CLASSES_ROOT\Directory\shell\runas]  
[HKEY_CLASSES_ROOT\Directory\shell\runas]  
@="Open cmd here as Admin"  
"HasLUAShield"=""  
[HKEY_CLASSES_ROOT\Directory\shell\runas\command]  
@="cmd.exe /s /k pushd \"%V\""  
[-HKEY_CLASSES_ROOT\Directory\Background\shell\runas]  
[HKEY_CLASSES_ROOT\Directory\Background\shell\runas]  
@="Open cmd here as Admin"  
"HasLUAShield"=""  
[HKEY_CLASSES_ROOT\Directory\Background\shell\runas\command]  
@="cmd.exe /s /k pushd \"%V\""  
[-HKEY_CLASSES_ROOT\Drive\shell\runas]  
[HKEY_CLASSES_ROOT\Drive\shell\runas]  
@="Open cmd here as Admin"  
"HasLUAShield"=""  
[HKEY_CLASSES_ROOT\Drive\shell\runas\command]  
@="cmd.exe /s /k pushd \"%V\""
```

- 去掉该选项的方法,新建uncmd.reg，保存好双击运行即可
```
Windows Registry Editor Version 5.00   
; Created by: Shawn Brink  
; http://www.sevenforums.com  
; Tutorial: http://www.sevenforums.com/tutorials/47415-open-command-window-here-administrator.html  
[-HKEY_CLASSES_ROOT\Directory\shell\runas]  
[-HKEY_CLASSES_ROOT\Directory\Background\shell\runas]  
[-HKEY_CLASSES_ROOT\Drive\shell\runas]
```