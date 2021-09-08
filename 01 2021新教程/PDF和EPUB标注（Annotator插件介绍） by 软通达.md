---
title: 
uid: 202109042041
aliases: []
tags: []
from: 
---
# 引言
在笔记软件中进行电子书阅读，并能实现批注、定位、引用多种功能，是许多笔记使用者或科研工作者的刚需。在obsidian中，我已经介绍了[[Mark mind（思维导图插件）]]（[[PDF标注（Mark mind插件） by 软通达]]），该插件目前又更新到1.0.0版本，大家有感兴趣可以去更新一下，好像又一些新功能。

今天介绍Annotator插件，该插件基于[[Hypothesis（软件）]]上进行开发整合，不仅能实现PDF批注，还能批注EPUB，缺点是目前无法实现PDF内的截图。

# 插件名片
Annotator插件是由Elias Sundqvist开发的一款插件，目前版本0.1.0。

Github地址： https://github.com/elias-sundqvist/obsidian-annotator

蓝奏云地址： https://wws.lanzoui.com/ijfWVtmctna

# 实际操作
## 在Yaml中输入语句
安装并启动插件后，在yaml区域输入一个`annotation-target`字段，例如
```
---
annotation-target: Attachment/elias-sundqvist_obsidian-annotator.pdf
---
```

上面代码中`Attachment`为我库中的附件文件夹，`elias-sundqvist_obsidian-annotator.pdf`为要批注的PDF名字。

输入完毕后，点击右上角的按钮，下面会 出现Annotate的选项。如果没有该选项，请检查插件是否安装，yaml语法是否正确。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210904210311.png)

## 在PDF中批注
点击Annotate选项后，进入阅读和批注视图。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210904210455.png)

划选文字后有批注（Annotate）和加亮（Highlight）两种选择。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210904210541.pn
g)

点击批注（Annotate），在框内输入批语，点击Post to only me，就可以完成保存。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210904210715.png)

## 返回markdown格式
点击右上角按钮，点击open as MD，就能返回md格式。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210904210851.png)

在编辑模式下，文字的可读性很差，需要切换到浏览模式。点击Show annotation，就能跳转到PDF上了。

注：可能是PDF或插件有问题，所以批注上出现了一些奇怪的东西。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210904211203.png)


