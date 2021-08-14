---
title: 
uid: 202105012136
aliases: []
tags: []
from: 
---
# 引言
我在之前有介绍过obsidian插件系统，可能是时间已久obsidian软件有许多改变，也可能是写的不够详细导致很多群友还是再问相关的问题，今天我重新介绍如何安装obsidian插件。

# 关闭安全模式
要启用第三方插件的第一步就是要关闭“安全模式”。点击左下角的设置-第三方插件-安全模式-关闭。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210501214150.png)
然后会有以下提示窗，选择关闭安全模式。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210501214258.png)
然后就能看到第三方插件一栏中多了一些选项。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210501214352.png)

# 获取obsidian插件
当我们关闭安全模式后，就可以加载我们的ob插件了。获取obsidian插件的渠道有2种：
- 从上图中的“社区插件”，直接加载ob官方渠道。但此数据存储在国外github的服务器上，可能存在网络问题。
- 手动下载安装包。

# 从“社区插件”安装
点击社区插件旁的“浏览”
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210501214707.png)
如果网络正常，则会正常显示社区中的插件，从左侧选择插件，在右侧点击安装即可。这是最简单的方式。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210501215003.png)
如果存在网络问题，在右上角会出现“无法加载社区插件”的通知。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210501214817.png)
如果你选择从社区安装，下面的内容就可以跳过了。

# 手动安装
如果存在网络问题（或者该插件没有上架社区插件频道），我们就要手动下载插件的安装包，自己安装到obsidian中。

## 下载插件安装包
如何下载插件的安装包：
- 自行到Github下载，但有时访问github也存在网络问题，请自行百度解决。
- 往期微信推文中，我一般会将插件安装包上传到国内的云盘，方便大家下载。
- 前往obsdiain的QQ群（774176839），在群文件中检索，如果检索不到，可以求助其他群友。

## 从Github下载的示例
在github的检索栏，检索obsidian就能得到相关的讯息，包括了插件和主题等等。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210501215515.png)

我以最近比较火的看板插件为例，它的github仓库是 https://github.com/mgmeyers/obsidian-kanban 。

登陆该仓库，点击右侧的“release”
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210501215637.png)

之后就能看到该插件不同的发行版本，例如下图显示的有0.1.2版本、0.1.1版本。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210501215745.png)
请注意上图红框部分，ob的插件主要有3类文件，命名为`main.js`、`manifest.json`、`styles.css`，也有些插件可能没有其中的某个文件。请将上述3个文件下载到本地，请勿重命名，然后新建一个文件夹将上述的文件放入。文件夹的名字需要是英文。一般我是以库的名称中非obsidian的字段来命名，例如这个库叫`obsidian-kanban`，我就把这文件夹命名为`kanban`。

## 将插件文件夹拷贝到ob库文件夹内
最后一步，我们需要将obsidian的插件文件夹拷贝到ob库文件夹内（注意不是位于C盘的ob软件安装文件夹！）。
下面以上述的kanban插件文件夹为例。我新建的obsidian库文件夹放在桌面，库的名称是“落山鸡”。我在文件管理器中，进入桌面，找到我新建的这个ob库。双击进入`.obsidian`文件夹。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210501221246.png)
在`.obsidian`文件夹内新建一个`plugins`的文件夹。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210501221434.png)
将刚刚kanban文件夹（或者你下载好的文件夹）复制到`plugins`的文件夹内。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210501221522.png)
请注意插件文件夹内不要再有文件夹了，直接就是刚刚下载好的`main.js`、`manifest.json`、`styles.css`三个文件（有些插件可能是两个）。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210501221634.png)

## 重启obsidian
第一次启动插件，需要重启obsdiain软件本体。重启后，在第三方插件中就能看到更多信息。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210501221814.png)
上图左箭头代表刷新插件文件夹，这样以后就不用重启ob软件也能刷新插件。
上图右箭头可以直接打开插件文件夹放置位置。

最后一步，我们还要点击插件右边的开关按钮，启动插件。这样插件就能正常运行了。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210501222020.png)


