---
title: 
uid: 202104050938
aliases: []
tags: []
from: 
---
[[软通达]]
# 摘要
本文介绍了obsidian的主题设置，推荐了相关的CSS资源和一些网页设计的教程。本人还是建议不要过多追求笔记样式，应该多做笔记。

# 引言
obsidian是基于Electron（软件架构）搭建的一款笔记软件，markdown可以视为一种简单的html网页语言（例如md中的`#`相当于html`<h1></h1>`），而css是常用于修饰html样式的语言，理论上软件各处的样式可以通过css来进行调节。更多关于html和css的专业论述，可以参见以下几个信息源：
- 菜鸟网： https://www.runoob.com/html/html-tutorial.html
- w3cSchool: https://www.w3school.com.cn/html/index.asp
- 其他相关专业的书籍，在京东上已有很多。

然而系统学习html和css对于大部分人是有难度和门槛的，而且我也不建议普通的笔记使用者深入了解，我们可以直接通过使用他人调试好的css，例如由whyt-byte（FFF大佬）编写的Blue-Topaz（蓝色托帕石）就是不错的选择。该CSS的Github下载地址： https://github.com/whyt-byte/Blue-Topaz_Obsidian-css ，蓝奏云地址： https://wws.lanzous.com/imLARohvvjc 。蓝色托帕石CSS中的备注详实，也方便了使用者进一步进行个性化修改。

# obsidian外观系统介绍
## 主题明亮和字体大小调整
点击左下设置-点击外观，就可以进入obsidian的外观设置系统，在这里可以修改调用的css文件。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210425222031.png)

- 基础颜色：如果css有明、暗两种配色，可以通过这里进行修改。明亮效果如下：
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210425222213.png)
- 使用“obsidian.css”主题文件：请关闭此选项。这好像是旧版本遗留下来的选项，目前新版本已无效且可能会有干扰。
- 半透明效果：建议关闭。开启后可能会耗费资源。
- Font size：调整字体大小。
- Quick font size adjustment：开启后可以通过Ctrl键+鼠标滚轮/触控板快速调整字体大小。

## 调用CSS
之后的选项就是调用CSS的区块，可以分为主题和代码段两部分：
- 主题CSS一般规定的内容比较多，代码大，有上百行。
- 代码段则是为了某个需求而定制的，例如下中的代码段就是为了去除一级标题，代码段一般在10行以内。代码段的优先级会高于主题CSS，即当两者冲突时以代码段的设置为准。可以理解为代码段是来修饰主题CSS。



![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210425222703.png)

点击上图中的①和③箭头所指的文件夹，就能打开相应的文件夹，将下载好的css放入文件夹后，点击旁边的刷新按钮就可以读取到。

对于主题CSS，可以点击②箭头所指的下拉菜单，进行选择，其中“无”代表的是obsidian的原生css。
对于代码段，可以点击旁边的按钮启用或关闭。


## 下载CSS
主题CSS的下载可以通过官方的社区主题，但大家可能会遇到网络问题无法访问，建议还是直接前往github检索`obsidian css`或者在QQ群的群文件中下载CSS文件。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210425223844.png)

片段CSS的资源也能在github下载得到，例如 https://github.com/deathau/obsidian-snippets 。

## 通过Minimal Theme Settings插件修改
obsidian的Minimal Theme Settings插件可以对CSS进行一些简单的操作，该插件的Github地址为 https://github.com/kepano/obsidian-minimal-settings 。
但Minimal Theme Settings插件正如其名，主要是为Minimal Theme主题服务，对于其他主题的css支持如何，大家请自行体验。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210425224842.png)

## 通过控制台进行调整
在win下通过`Ctrl+Shift+I`可以打开控制台（一种调试网页html的工具），然后可以通过控制台来对相关的元素进行修改（懂的人都懂，不懂的人就不要尝试了，或者先自学Html和CSS）。
以下图为例，可以看出`obsidian主题设置`所在元素在html中的位置。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210425225156.png)



# 相关视频资源推荐
目前B站上已经有很多obsidian的视频，大家可以去检索，我检索到以下2个视频推荐给大家
- 给笔记的列表加上漂亮的层级线条 | 笔记神器 Obsidian 完全指南，胸毛齐腰， https://www.bilibili.com/video/BV1a5411w7DF
- 如何给obsidian换主题｜最美主题都在这里｜小白新手入门obsiidian，aliya成长记， https://www.bilibili.com/video/BV1354y1a75d

另外QQ群中也在征集相关的CSS片段，以丰富和简化个性化的设置。大家有好的资源欢迎上传。



