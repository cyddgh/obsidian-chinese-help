---
title: 
uid: 202107151215
aliases: []
tags: []
from: 
---
[[软通达]]

# 摘要

本文介绍了obsidian官方的同步服务（Sync），早鸟价为4美元一个月，能提供同步、历史版本等功能。

  

# 引言

obsidian是一款基于本地的笔记软件，但不意味其不提供互联网服务，除了之前已经介绍的发布服务外，ob还有同步服务，早鸟价为4美元一个月（按年付），按月付的早鸟价是5美元一个月（以上价格请见官网说明，本文不予保证）。官网地址：https://obsidian.md/pricing

  

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210121145440.png)

  

# 实际操作

在进行下列操作前，你需要先注册一个ob的账号，然后使用该账号购买同步服务，之后才能享受ob的同步服务。

## 开启Sync（同步）服务

点击设置-核心插件-Sync

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210121110438.png)

  
  

## 设置同步服务

在插件选项-Sync中进行同步服务的设置

因为目前还未汉化，我对相关服务进行一些说明：

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210121110550.png)

### Pick Remote Vault

点击Choose（选择）后，会弹出以下对话框，显示目前连接的是哪个笔记。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210121110848.png)

点击Create remote vault（创建远端库），进入以下界面

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210121111045.png)

- Vault name：设置库的文件名，随意

- Customize end-to-end encryption password：设置端到端加密，增强笔记的安全性。我的理解是，设置了端到端加密，这样ob官方就无法查看你的笔记，笔记将以密文形式保存在云端。

- Encryption password：如果你选择了端到端加密，则需要在这里输入你要设置的密码。如果你不选择端到端加密，就无需输入密码。

  

## Sync status（同步状态）

如果显示“Obsidian Sync is currently running”（ob同步服务正在运行），就说明同步服务正常。点击Pause（暂停）可以暂停同步的服务，暂停后显示如下。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210121112534.png)

  

## Deleted files（恢复已删除文件）

这一栏是用于恢复已删除的文件，并能回滚到相关文件的历史版本。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210121143802.png)

点击

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210121143915.png)

  

## Sync activity（同步状态）

这一栏能看到目前ob的同步状态，哪些文件同步上云端，哪些文件同步出错。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210121144256.png)

  

## Selective sync（选择性同步）

obsidian可以支持部分同步，可以排除某个文件夹使之不能上传，也选择某一类型的附件进行上传。如下图所示，可以对图片、声音、视频和PDF进行选择性上传。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210121144659.png)

  

# 未完待续

因为篇幅原因，还有一些对同步的体验和看法留在下一篇中讲述。