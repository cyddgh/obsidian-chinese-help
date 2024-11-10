---
title: 
uid: 202408181309
aliases: 
tags: 
from:
---
#### 摘要
本文介绍了Mefo白板软件中部分的编辑功能（提示潜在的双链），obsidian中的Virtual linker插件能复刻该功能。个人认为大大优化了双链的使用和编辑体验，推荐大家安装使用。

#### 正文
最近，看到一款的白板软件Mefo（ https://mefo.cc/ ，注册时邀请码： lQCbwK ，有送30天的会员）。它的一些白板编辑上的体验很不错，有看到设计上的思考。最令我眼馋的效果是：在页面上的文字如果有这软件中匹配到相应标题的卡片，就能有一个下划线提示，让你可以跳转，具体如下图：

![](https://gitee.com/cyddgi/picture-store/raw/master/img/2024/202408/202408181317763.png)

可以看到这“双链软件”这卡片内容中，当我提到了obsidian时出现了下划线，这是因为软件中存在另一张名为“obsidian”的卡片。这就方便了不同卡片之间的链接。

然后过几天，就看到了PKmer的推文，介绍了一款ob的插件[[ Virtual Linker Plugin (Glossary Plugin)]]，也能实现类似的效果，于是撰写了本文。（上篇文章还说，好久没看到让我心动的插件，没想到更过一周就看到了。）

#### 插件信息
插件名称：Virtual Linker Plugin (Glossary Plugin)
插件作者：vschroeter
插件地址：https://github.com/vschroeter/obsidian-virtual-linker

#### 实际操作
插件的操作很简单，安装后就可以使用了。但在一开始我和一些人有遇到安装后无效果的问题，我个人是升级了ob的程序后解决，不清楚具体的细节。

启用插件后，进入文档，如果卡片内容中的文字与ob库中的某张卡片标题同名，自动会出现一个链接🔗的标志，如下图。
![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/2024/202408/202408181324548.png)

在出现链接的相关字段，按住Ctrl，就能出现相应的卡片信息，这是最近ob的编辑器升级（吸收了[[Hover editor（悬浮编辑插件）]]），如下图。
![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/2024/202408/202408181327112.png)

并且这种效果在白板中也能实现，如下图。
![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/2024/202408/202408181330323.png)

#### 结语
这个插件大大方便了双链的阅读和编辑操作，提升了ob使用的幸福感。

另外，Mefo软件的一些设计，我认为也提升了白板软件的一些体验，除上面的功能外，像这不同画板中的提示功能也不不错。如下图显示，卡片“全球变化问题”不仅仅在当下“生态学”的白板中存在，在“省基金”的白板中也存在，同理“城市化”卡片也在“省基金”和“苔藓学”两个白板中存在。是否有哪位ob插件的开发者也能出一款类似的插件呢？或者已有类似的插件，也请读者留言。

![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/2024/202408/202408181331051.png)
