# Win10下OpenCV在visual studio上的配置<br>
## OpenCV相关库下载方式<br>
1.从[官网](http://opencv.org/) :http://opencv.org/ 下载需要类型的安装包.进去后选择Releases（发行）菜单即可选择所需版本的库。<br>   

2.在GitHub上搜索opencv出来的第一个和第二个项目就是opencv和opencv-contrib（opencv扩展库），进去后点击tag下拉选项选择需要的版本下载即可。<br>

## 版本选择<br>
这里涉及到了OpenCV对VC版本的支持情况<br>

首先了解下VS(Visual Studio)与VC(Visual C++)版本对应关系：（Microsoft Visual Studio是一个很大的开发环境，包含很多高级语言的开发环境，VC只是VS其中的一个开发环境。)<br>
        Visual Studio 6 ： vc6
        Visual Studio 2003 ： vc7
        Visual Studio 2005 ： vc8
        Visual Studio 2008 ： vc9
        Visual Studio 2010 ： vc10
        Visual Studio 2012 ： vc11
        Visual Studio 2013 ： vc12
        Visual Studio 2015 ： vc14
        Visual Studio 2017 ： vc15
        Visual Studio 2019 ： vc16
        
后续在自己使用的VS版本中配置opencv选择动态链接库路径时需要根据自己的VS版本选择对应的VC文件夹。<br>

VS2013可以下载opencv-2.4.13或者opencv-2.4.10版本。vs2015或vs2017就需要使用3.4.0以上的版本。<br>

## 配置方法<br>
### 1.使用现成的安装包配置<br>
配置方法有正常配置和一劳永逸配置两种方法，推荐使用一劳永逸配置方法，配置一次，以后新建工程之后只需一键添加配置好opencv路径的项目属性表在工程中即可。<br>

从官网下载的安装包解压后本地路径假设为D:\opencv。首先配置系统环境变量，右键单击“计算机”，选择“属性”，进入属性窗口，左键单击“高级系统设置”，进入“系统属性”对话框，左键单击“环境变量”，双击"Path"编辑，添加路径D:\opencv\opencv\build\x86\vc12\bin。添加完成后重启电脑。<br>

接下来在vs中的配置参考该[配置文档](https://blog.csdn.net/tercel_zhang/article/details/42041447)即可。<br>

**注意：**  
以后可能会配置不同opencv版本、debug/release、cuda版本、带有三维点云处理模块viz、带有三维显示功能的gl库等等的具有不同开发功能的opencv，为了方便使用不混淆，在给属性表命名的时候最好写上这个opencv库的版本、debug/release以及特殊扩展功能。<br>

### 2.利用CMake编译<br>
如果在程序里面需要使用opencv其他的库或者配置GPU版本的opencv就需要自己使用CMake编译自己的安装包.<br> 

编译过程大同小异，具体操作将在另一篇文档“GPU版的opencv的配置.md”中分享.<br>
