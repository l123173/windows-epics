# windows-epics

### 一开始用网上的例子，用的是stabery（没有使用vs），错误了；
后来有选择了vs2022（太大），结果里头没有vsxxx.bat，又新装了vs的工具，有了vsxxx.bat工具；
其实用Chocolatey应该能解决，后面看到Chocolatey里有vs的c++ tool。
处了ccl.obj错误，因为cmd的cl命令都没有，修改了以后，还是有stdio.h，assert.h等诸多问题，无人可解决，遂放弃。

### 使用Chocolatey 安装了msys2（单独安装也行）
参考这个网站去做，一个个word的看，https://docs.epics-controls.org/projects/how-tos/en/latest/getting-started/installation-windows-msys2.html
（ 注意他的32,64位写反了，32位才是i686,64位是x86_64 ）
强调一点，打开mysy64.exe，一直都是用这个虚拟的linux环境中去make。  
无报错。  
**关于环境变量 看我这里好了**
配置一个windows环境变量 MSYS2_PATH_TYPE, 值为inherit。然后windows里面，添加epics的即可。


但是mysy的操作有些不一样，例如：  
更新msys2的软件列表：pacman -Sy
查找相关软件：pacman -Ss vim
然后执行安装命令：pacman -S vim

