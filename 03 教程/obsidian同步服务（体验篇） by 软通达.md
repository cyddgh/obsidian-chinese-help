---
title: 
uid: 202107151216
aliases: []
tags: []
from: 
---
[[软通达]]

# 摘要

本文主要介绍obsidian同步服务在日常使用提升（端到端加密、历史版本和多设备同步）以及我个人的体验。

  

# 引言

昨天已经介绍了如何设置obsidian同步服务，今天这篇文章主要介绍obsidian同步服务对日常使用有何帮助。对于ob同步服务带来的功能提升，是否值得每月4美元（早鸟价），就看大家自己的判断了。

在阅读本文前，可能需要提前阅读昨天的推文。

  

# obsidian同步服务带来的功能提升

## 端到端加密

如果设置了端到端加密，当你之后点击Connect（连接）后，ob需要你输入密码才能访问远端库。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210121111555.png)

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210121111659.png)

输入密码后，就可以开始同步

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210121111735.png)

目前正在同步的库，会显示Connect

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210121111824.png)

同时，如上图所示，ob同步服务可以支持多个库的同步，如“ChenNote”是私人笔记的笔记库，而“ObHelpDocument”是ob教程的笔记库。据说，ob同步服务最多可以支持5个不同库的同步（未测试）。

  

## 历史版本

当你启动了同步服务后，可以点击笔记右上角的更多设置-View version history（查阅历史版本），查阅该笔记的历史版本。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210122092521.png)

目前的历史版本记录很快，大纲输入一行文字就可能被记录一次历史版本，这样可以防止文档输入到一半丢失的情况。如下图所示，从35分到36分ob就为我的笔记构建了5个历史版本。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210122092834.png)

  

# 同步小标签

当你使用了ob同步服务后，在ob的右下角会一个绿色打勾符号，这个符号代表同步完成。

如果出现问题，可以前往Sync activity查看具体出现了什么问题。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210122092013.png)

  

## 多设备同步

多设备同步目前只支持不同电脑（PC或Mac）之间进行ob库的同步，但我更期待使用ob同步服务进行电脑和手机之间的同步。因为手机app还未面世，具体的使用等以后再撰文。但可以进行合理的推测，使用官方的同步服务，我们能最好地完成设备之间的同步。

  

# 个人感想

obsidian所提供的同步服务能解决以下几个免费版的痛点：

- 没有同步服务，只能单机使用。

- 没有版本控制，无法进行文件追溯。

  

但上述痛点，目前已经可以通过坚果云、git、OneDrive等同步服务来解决。但第三方的同步服务在使用中还是有所不足，例如ob文件可能被莫名锁定。同时，ob同步服务更重要的功能可能是对未来的ob手机app的支持。