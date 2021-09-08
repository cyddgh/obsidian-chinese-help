---
title: 
uid: 202107250834
aliases: []
tags: []
from: 
---

# 引言
今天开始会尝试将介绍一些obsidian的插件，并将之前的介绍也一起归类到“obsidian插件介绍”这一栏目。今天要介绍的是一款可以快速输入markdown格式的插件Markdown Formatting Assistant，具体的效果如下，可能类似于一些md软件的状态栏。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210131102128.png)

# 插件介绍
Markdown Formatting Assistant是由Reocin编写的，具体的Github地址： https://github.com/Reocin/obsidian-markdown-formatting-assistant-plugin ，此时的版本是0.1.2。

## 具体操作
开启插件后，在软件右侧的side pane（显示双链、标签、大纲的地方）会出现新的一栏，显示了许多md的格式，直接点击就能快速输入到md中。
目前包含的md格式包括了：1-6级标题、粗体、斜体、划线、代码块、引用、插入图片、有序列表、无序列表等等，对于新手非常友好。

此外更为惊艳的一个设计是，在md中输入`\`就能弹出一个下拉选框，有一点notion的感觉。感觉插件的开发者们可以利用好这一设计，使得用户能快速输入一些代码。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210131102940.png)

## 插件设置
插件的设置非常简单：
第一行是设置触发下拉选单的命令，默认是`\`，如果与你的习惯不符，可以进行修改。
第二行是设置md的面板显示在何处（？）。
我个人没有去修改以上的选项，都采用了默认的设置。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210131103237.png)

# 个人的话
这软件对于md新手可能是有帮助的，可以免去学习md语法的过程。当然一些已经熟知md语法的用户就无需此插件了。对于md软件是否需要一个快速输入的md格式命令的状态栏，大家也多有争议，我个人目前在用的其他md软件，如Gingko、Gridea都是没有像Typora有一个状态栏。

此外，对于插件的安装，我个人建议还是通过ob软件安装（设置内的第三方插件-社区插件-浏览），具体的安装步骤和无法加载社区的解决方法都已成文大家可以翻阅之前的文章。
