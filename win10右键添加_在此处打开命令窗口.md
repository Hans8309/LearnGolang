# win10右键添加 “在此处打开命令窗口”

参考： https://blog.csdn.net/myr503270510/article/details/109514806?utm_medium=distribute.pc_relevant.none-task-blog-title-10&spm=1001.2101.3001.4242

参考： https://blog.csdn.net/sinat_32238399/article/details/85927822?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.add_param_isCf&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.add_param_isCf

Windows10 - 在当前文件夹下打开cmd（命令行）的方法：

1. 在浏览器中打开当前目录，在路径栏内，清除文件路径输入cmd,回车即可打开终端窗口
2. 在浏览器的当前目录空白处，按住shift，再点击鼠标右键，选择右键菜单“在此处打开Powershell窗口.
3. 在右键菜单中增加“在此处打开命令窗口”，具体方法如下:

第一步： 新建一个txt文件，文件名为OpenCmdHere
第二步： 用记事本打开OpenCmdHere.txt文件，将如下代码复制进去，打开“另存为”对话框，将编码格式设置为ANSI后保存.

```
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\Directory\shell\OpenCmdHere]
@="在此处打开命令窗口"
"Icon"="cmd.exe"

[HKEY_CLASSES_ROOT\Directory\shell\OpenCmdHere\command]
@="cmd.exe /s /k pushd \"%V\""

[HKEY_CLASSES_ROOT\Directory\Background\shell\OpenCmdHere]
@="在此处打开命令窗口"
"Icon"="cmd.exe"

[HKEY_CLASSES_ROOT\Directory\Background\shell\OpenCmdHere\command]
@="cmd.exe /s /k pushd \"%V\""

[HKEY_CLASSES_ROOT\Drive\shell\OpenCmdHere]
@="在此处打开命令窗口"
"Icon"="cmd.exe"

[HKEY_CLASSES_ROOT\Drive\shell\OpenCmdHere\command]
@="cmd.exe /s /k pushd \"%V\""

[HKEY_CLASSES_ROOT\LibraryFolder\background\shell\OpenCmdHere]
@="在此处打开命令窗口"
"Icon"="cmd.exe"

[HKEY_CLASSES_ROOT\LibraryFolder\background\shell\OpenCmdHere\command]
@="cmd.exe /s /k pushd \"%V\""
```

第三步： 将txt文件后缀名更改为 reg
第四步： 双击OpenCmdHere.reg文件运行
至此，就已经添加好啦
