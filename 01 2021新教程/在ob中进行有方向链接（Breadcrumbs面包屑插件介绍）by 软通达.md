---
title: 
uid: 202201171746
aliases: []
tags: []
from: 
---

# 引言
在以往文章中，我多次提到如何优化图谱，其中一种方法是thebrain的带方向链接。而目前obsidian中可以使用Breadcrumbs（中文名：面包屑）插件来实现链接的方向性。

这插件是21年9月左右出来，但不知道为什么在我的库中出现了无法使用的问题，且不同库的问题还不同，基于稳定性考虑，当时没有推荐给大家（目前依然存在这问题）。当时风尘噗噗已经在B站上做了一个视频教程——“在obsidian中实现笔记层级 (breadcrumbs插件介绍)”（ https://www.bilibili.com/video/BV1KL411s7bX ）很详细介绍了这个插件，大家也可以去看看，本文具体操作讲解并不多。

近期，我看了Obsidian Community Talks的视频“Breadcrumbs - Everything you need to know” （ https://www.youtube.com/watch?v=N4QmszBRu9I ）上手使用了一下，这插件已经可以在存放有我主要笔记的库中稳定运行了，但在“ob中文教程”库无法运行。

本文只是大致介绍一下这插件，对于内部的许多设置，我本人没有使用，更多的设置可以参考上面两个视频。


# 插件名片
Breadcrumbs插件是由SkepticMystic开发，目前版本是2.39.3。

Github地址： https://github.com/SkepticMystic/breadcrumbs

# 实际操作
## 设置介绍
Breadcrumbs插件实现有方向链接方法是基于YAML中的相关字段。这些字段可以自己在插件设置中的Hierachies中进行修改，还可以有多套字段同时存在。

目前默认的字段有up、same、down、next、prev，其中next和prev是新添加的。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220117175608.png)


但是如果使用Yaml字段作为标记，那么文档名一旦改变，因为yaml中的双链不会随着改变，会导致yaml的消息失去链接。因此建议使用dataview的`::`符号来进行链接。如果要使用`::`来进行标记，必须安装并开启dataview插件。

## 操作介绍
下面简单介绍一下这插件的用途。更详细的使用，可以直接看风尘噗噗的视频教程——“在obsidian中实现笔记层级 (breadcrumbs插件介绍)”（ https://www.bilibili.com/video/BV1KL411s7bX ）。

例如，我的库中有以下md文件：“000 我的知识树（HOME）”、“摄影（MOC）”、“摄影教程”、“摄影论坛”、“英语学习（MOC）”。我期待这5个md文件有如下的层级关系。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220119134808.png)

为此，我在“摄影（MOC）”这一md中输入以下内容
```
up:: [[000 我的知识树（HOME）]]

down:: [[摄影教程]]
down:: [[摄影论坛]]
```

在“英语学习（MOC）”这一md中输入以下内容
```
up:: [[000 我的知识树（HOME）]]
```

这样就构建了上图的层级关系。

并且因为“摄影（MOC）”和“英语学习（MOC）”都隶属“000 我的知识树（HOME）”（或说是在“000 我的知识树（HOME）”的down位），打开插件视图时，“英语学习（MOC）”会位于“摄影（MOC）”的same位。这逻辑如同thebrain。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220119135558.png)

并且，该插件还自带图谱功能，进入Breadcrumbs Visualisation，可以看到相关的图谱信息。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220119135847.png)


Breadcrumbs的图谱展示：

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220119140020.png)



# 个人的话
我个人非常喜欢Breadcrumbs插件，它是一个能提高ob链接质量的插件，能使之更接近thebrain。最近新增的Prev和Next字段，感觉可以作为卢曼序列的实现手段。
