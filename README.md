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



------------------------------  
## 以下是2023年的操作  
### 不要用vs这种方法安装了  
但还是简述以下vs安装的过程和坑
其实主要是解决ccl.obj（这个据说使用mingw的某个版本的时候有这个问题） 和cl.exe的问题。  
第一次好不容易成功以后，再make，居然又错了，实在不知道咋解决，放弃了。另外，用vs其实不如用mingw的方法好，mingw其实就是linux环境，那样比较好一些。  
1) windows里echo %path% 是查看环境变量  
2) vs 一定要安装c++ tools，还有桌面的那个
3) gmake这个，其实直接下载一个exe，然后编辑环境变量就行了  
4) 不需要使用choco，直接自己安装就行了
5) bash 去掉最前面的echo off就是调试模式
6) bash 里如果不认识中文，可以在最前面输入 chcp 65001  （好像，灵过，但是最后删掉了也能用）
7) http://www.manongjc.com/detail/41-wkubvssdpavrzpr.html
call "C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Auxiliary\Build\vcvarsall.bat" amd64 10.0.22621.0 -vcvars_ver=14.35
