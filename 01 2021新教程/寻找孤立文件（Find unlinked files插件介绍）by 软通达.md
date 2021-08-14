---
title: 
uid: 202107272157
aliases: []
tags: []
from: 
---
# 摘要
本文介绍了Find unlinked files插件，该插件能查找并删除孤立文件，可用于清理无关图片。

# 引言
Find unlinked files插件已经问世很久了，因为太简单所以一直没有介绍，但一直有ob新用户在问。而常常又记不住名称，所以写下本文方便后来人。
如果你是经常插入本地图片，担心一些文档删除后导致图片冗余，就可以用到本软件。

# 插件名片
Find unlinked files插件是由Vinzent03开发，目前版本是1.2.1。

Github地址： https://github.com/Vinzent03/find-unlinked-files

蓝奏云地址： https://wws.lanzoui.com/iswOPrxf2pc

# 实际操作
本插件会查找整个库中没有和其他文件产生链接的文件，然后创建一个列表让你可以删除或移动。
仅适用于ob 0.9.7以上版本。
按Ctrl+P进入命令模式，找到`Find unlinked files`
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210727220727.png)
有3种模式：
1. Find unlinked files：找到没有产生链接的文件，运行之后会生成一个.md文档。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210727221103.png)

2. Find unresolved links：找到那些在文库中出现但没有创建文件的双链。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210727221235.png)

例如，上图中显示的`[[Advanced Tables（表格输入插件）]] in [[02 名词解释/Obsidian插件列表与教程（MOC）]], [[02 名词解释/ob中提升编辑体验的插件]]`，就是说在`[[02 名词解释/Obsidian插件列表与教程（MOC）]], [[02 名词解释/ob中提升编辑体验的插件]]`中存在的双链文件`[[Advanced Tables（表格输入插件）]]`并没有被创建。

3. Delete unlinked files with certain extension. See README. 删除无链接的指定类型文件。具体在插件设置面板指定文件类型，例如，在红框中输入`jpg,png`两种格式。请注意虽然默认设置看上去里面有填写文字，但实际为空，只是为了告诉你这里该填写什么。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210727221747.png)

要运行此命令，还需要提前运行`Find unlinked files`命令，否则会出现如下报错。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210727221808.png)

如果运行成功，则会弹出信息框让你进行确认（Confirm），将文件删除。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210727222243.png)
