---
title: 
uid: 202108232316
aliases: [双开ob]
tags: []
from: 
---
# 摘要
使用映射虚拟磁盘的方式，实现多个obsidian软件读取同一个ob库。

# 引言
因为有些obsidian使用者同时使用两个屏幕，所以希望同时打开两个obsidian软件对同一个库进行操作。但目前ob还支持软件多开的操作，所以本文尝试将文件夹映射虚拟磁盘的方式实现在win系统下的ob多开功能。

**警告**：本操作可能存在未知风险。虽然我本人认为较为安全，且没有遇到什么问题，但可能存在某种风险，请谨慎使用。

该过程的机理可能涉及软连接、硬链接、符号链接，如果感兴趣可以去看“符号链接、硬链接及其在 Windows 上的应用举例”（ https://sspai.com/post/66834 ）。我个人对此不是很了解，所以下面的术语可能存在错误，但操作应该是没有问题。

# 软件说明
本操作也可以使用cmd指令，因为是面对普通使用者，这里不过多介绍。本文采用的一款名为Virtual Driver的软件，该软件由sephil编写，蚕子推荐，本人正在使用该软件，但对此软件的安全性和代码问题不予保证。
开发者页面： https://www.cnblogs.com/sephil/archive/2008/11/30/nvd.html
蓝奏云： https://wws.lanzoui.com/ib7zat2xvkf

# 实际操作
## 映射文件夹
我的ob库放在：`D:\OneDrive\Obsidian`下的Obsidian-Working文件夹
启动Virtual Driver，我随意选择一个空的驱动器盘符（例如H），双击选中`D:\OneDrive\Obsidian`，点击确认，这样就将`D:\OneDrive\Obsidian`映射到H盘上，电脑上就会出现一个H盘的盘符。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210823233222.png)

## 打开两个ob
首先，打开ob软件，打开其中一个库，例如`D:\OneDrive\Obsidian\Obsidian-Working`。
然后点击左下角的“打开其他库”，选择“打开库文件夹”，选择映射的文件夹的位置，即`H:\Obsidian-Working`。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210823233934.png)

这样就完成了ob软件的多开了。

## 可能存在的问题
单独多开ob软件应该是没有问题的，但因为有插件的存在可能会导致一些冲突。
例如，git插件设置为每5分钟备份一次，但因为软件多开，存在多个git插件的5分钟即使，实际备份的步长可能会明显小于5分钟。


