# Ubuntu Installation and Configuration

## Ubuntu安装

### USB制作

[Create a bootable USB stick with Rufus on Windows](https://ubuntu.com/tutorials/create-a-usb-stick-on-windows#9-installation-complete)

参考官方教程，软件使用Rufus或UltraISO都可。

### Ubuntu安装

[使用软碟通(UItraISO)在一块U盘上制作Windows、Ubuntu双系统启动盘以及在移动硬盘上安装Ubuntu系统教程](https://zhuanlan.zhihu.com/p/466176757)

Ubuntu安装可以参考此博客，其中有关分区和启动引导项的内容请参考下一节``分区``内容。

### 分区

下面两篇博客介绍分区方案，有关Ubuntu分区的更多知识可以在《鸟哥的Linux私房菜》第二章中学习。

[Ubuntu 20.04 系统分区](https://blog.csdn.net/ISE_numberone/article/details/120165122)

[【第一篇】Ubuntu 16.04 服务器深度学习环境共用方案（搭建、分配、克隆、远程）](https://zhuanlan.zhihu.com/p/59559936)



使用SanDisk E61 1TB，最终分区方案：

- EFI 1G 主分区
- / 80G 主分区
- /usr 200G 逻辑分区
- /var 40G 逻辑分区
- /tmp 10G 逻辑分区
- Swap 16G 逻辑分区
- /home 500G 逻辑分区
- 未分配 剩余空间



需要注意，Ubuntu安装时需要把启动引导器装在EFI所在位置，否则由于缺少启动引导项会导致无法实现即插即用。

### 启动项修复

[Ubuntu装在移动硬盘或者U盘在任何电脑上使用](https://blog.csdn.net/qq_18941425/article/details/80502009)

启动项修复是为了实现移动硬盘插在其他电脑上也可以启动Ubuntu，这里需要用到`USB制作`中装好Ubuntu镜像的U盘。

P.S. 运行博客中代码时记得联网。



至此，Ubuntu安装完成，下一步将安装常用软件。

P.S，也可以参考王育文整理的安装教程[Ubuntu安装](https://faithful-efraasia-59a.notion.site/Ubuntu-6107a23b6b6b4449bd15e7be1776e2ec)

## 软件安装

常用软件可以在Ubuntu Software中进行安装，类似移动端的应用市场。

对于`.deb`文件，在文件所在目录打开终端`Ctrl + Alt + T`，使用`sudo dpkg -i xxx.deb`即可完成安装。

> 对于`.deb`文件，也可以选择安装`gdebi`，可以较为方便的进行安装。

或者使用`sudo apt-get install xxx`，也可进行软件安装。

其他情况可以参考软件官网的安装教程。

> [Linux(Ubuntu)不好用吗？是因为你没有安装这些软件](https://zhuanlan.zhihu.com/p/39052366)
>
> 这篇博客介绍了一些Ubuntu系统比较常用的软件。

### WPS

[ubuntu20.04安装WPS教程](https://blog.csdn.net/zeye5731/article/details/124486830)

完成WPS安装后需要添加缺少字体，参考博客即可。

### Chrome

[Ubuntu上安装Chrome浏览器](https://blog.csdn.net/howard2005/article/details/124906494)

### flashplugin

[ubunntu系统网页无法播放视频解决办法](https://blog.csdn.net/Time_Memory_cici/article/details/124583199)

安装该插件可以实现网页观看B站或其他视频网站视频

### MATLAB

[Matlab unable to install R2021b: "unable to write to selected folder" in Ubuntu 20.04](https://ww2.mathworks.cn/matlabcentral/answers/1619455-matlab-unable-to-install-r2021b-unable-to-write-to-selected-folder-in-ubuntu-20-04/?s_tid=mlc_lp_leaf)

如果想要在`/usr`中安装MATLAB，先参考此官方回答为安装操作授权。

[Ubuntu18.04 安装Matlab2021b](https://blog.csdn.net/qq_43309940/article/details/127027181?spm=1001.2014.3001.5501)

### 微信

[Ubuntu安装微信，三步到位](https://blog.csdn.net/m0_50502579/article/details/126096484)

美中不足的是表情包会有变形，建议还是在Windows系统下使用

### 福昕阅读器

[如何在 Ubuntu 22.04 LTS 上安装 Foxit PDF Reader](https://www.xtuos.com/5653.html)

### PDFtk

该插件可以用于Zotero茉莉花插件

[Install PDFtk on Ubuntu](https://linuxhint.com/install_pdftk_ubuntu/)

> 目前还没有完成Zotero茉莉花配置，后续会单独开一个Zotero插件配置的帖子。

### GitHub Desktop

[ubuntu 安装GitHub desktop](https://blog.csdn.net/qq_20477309/article/details/114199294)

还是建议使用命令行进行操作。

## 深度学习环境配置

安装顺序最好按照`显卡驱动+CUDA+cuDNN+深度学习框架`，Anaconda为可选项，目前还在学习当中，后续会继续更新

### 显卡驱动+CUDA+cuDNN

参考B站教程

[搭建舒适的Ubuntu使用环境系列——安装显卡驱动、CUDA、cuDNN及其简单介绍](https://www.bilibili.com/video/BV16Y411M7SC/?spm_id_from=333.788&vd_source=fa013dd1b93548577d70801e8af67c4a)

### Anaconda

[Ubuntu下安装Anaconda的步骤（带图）](https://zhuanlan.zhihu.com/p/426655323)

### Pytorch和Tensorflow

同样参考B站视频教程

[搭建舒适的Ubuntu使用环境系列——从零到一搭建深度学习生产环境(Pytorch、Tensorflow)并使用GPU版本，附详细文档(以Ubuntu系统为例)](https://www.bilibili.com/video/BV13Y411T71Y/?spm_id_from=333.788&vd_source=fa013dd1b93548577d70801e8af67c4a)

## 其他配置

### 时间同步

使用Ubuntu再切换回Windows系统时会出现时间不对的情况，使用以下代码即可
