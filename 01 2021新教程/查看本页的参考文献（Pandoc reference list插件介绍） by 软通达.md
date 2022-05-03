---
uid: 20220429154246
aliases: []
---

# 引言
Zettlr软件和bib、pandoc的结合非常不错，能显示页面中pandoc key引用的参考文献。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/202204291546256.png)

本文介绍中的Pandoc reference list插件为obsidian增加了这一功能。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/202204291553067.png)

# 插件介绍
Pandoc reference list插件，由mgmeyers开发，目前版本号为1.0.0。我是通过BRAT插件安装。

Github页面： https://github.com/mgmeyers/obsidian-pandoc-reference-list

# 实际操作

本插件属于增强型插件，应用在工作流的末端。使用本插件，你需要掌握的前置知识有bib文件和pandoc软件，这些知识你可以百度。

我的工作流是：zotero获取文献，zotero的Better BibTeX 插件将文献库导出成bib文件，然后使用本 插件读取该bib文件。

Pandoc reference list插件需要进行设置

![](https://gitee.com/cyddgi/picture-store/raw/master/img/202204291556457.png)

目前需要设置的有3个：
- Bib文件的地址：请输入你bib文件所在的文件夹路径，例如`D:\Documents\Desktop\我的文库.bib`。Mac系统请使用绝对路径，例如`/A 学术研究Research/我的文库.json`。
- CSL文件路径：可以放空，使用默认的参考文献格式就行。更多关于CSL的知识，可以去pandoc的手册中查询，或者百度。
- Pandoc路径：需要填写你的pandoc地址，如果已经安装了pandoc，这里自动会有地址，例如`C:\Program Files\Pandoc\pandoc.EXE`。有群友反馈，没有安装pandoc也能运行，期待大家后续的反馈。

配置好了，你在ob卡片中输入对应的pandoc的key，就能在右侧的References中看到对应的参考文献了。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/202204291606722.png)