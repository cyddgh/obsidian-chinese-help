---
uid: 20220319183150
aliases: []
---
本文所说的obsidian插件是ob第三方插件，因为ob核心插件是自带的。本文在中文教程中的uid为20220319183150。

其中，我之前的文章[[如何安装obsdiain插件]]，应该还算经典，本文应该是对其的进一步扩充。之后我又写了
- [[ob插件全列表]]
- [[为什么无法查看和下载社区插件和主题（MOC）]]
- [[为什么无法加载插件（Failed to load plugin）]]
- [[安装obsidian插件和主题（从Gitee下载） by 软通达]]
- [[安装测试版插件（obsidian42-BRAT插件介绍） by 软通达]]

此时做阶段性总结的原因是因为：
- 最近ob官方出了一个插件列表：  https://obsidian.md/plugins 
- [[obsidian42 Brat(安装测试版插件)]]很火

迫切希望有人能将Brat下载源定向到gitee，使得国内的ob用户能通过查询列表得到插件链接，在Brat输入链接从gitee下载和更新插件。不知道技术上是否可以实现。

# 最简单（也可能是最困难）的方式
通过ob内置的“第三方插件”-“社区插件”直接进行下载。但群友遇到的问题经常是无法打开，也就是存在网络问题。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220319183433.png)

为了解决这网络问题，可能有通过Quicker、修改hosts、[[FastGithub]]、[[Steam++]]。对于这些方式我了解不多，对效果存疑，新手就不要折腾这些了。

# 手动安装
## 全插件列表查找插件链接
首先，要先通过[[ob插件全列表]]来查询ob插件的下载链接（以下选一即可）：
- ob官方的列表：  https://obsidian.md/plugins 
- 宏沉一笑维护的列表：  https://gitee.com/whghcyx/obsidian-plugin/blob/master/%E6%8F%92%E4%BB%B6.md ，以及一个在线文档： https://docs.qq.com/sheet/DUVpCS3ZTTnJrTFpV&scene=cae366bda12e2556a7ab0220tL1To1 
- Johnny学的列表： https://airtable.com/shrdmp10Lxmf5Wmgl/tblJqnWpcKURTjysX 或  https://ob.pory.app/

## 下载插件安装包
如果是从github下载，记得是从“release”中下载，更多信息请见[[如何安装obsdiain插件]]。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210501215637.png)

新手可能找不到插件安装的文件夹，是因为该文件夹还没创建。建议先选择一个[[ob开箱即用库]]开始，要新潮一些的可以选[[开箱即用库（Blue topaz examples）by Cuman]]，我做的库功能可能保守一些[[obsidian开箱即用库 by 落山鸡]]。


# 通过BRAT插件维护
[[obsidian42 Brat(安装测试版插件)]]是最近很火的一个插件，目前很多人都在使用，但它的下载源还是github，可能有网络问题。希望以后有人魔改一个，将下载源指定到gitee，方便国内的使用者。

更多信息可见[[安装测试版插件（obsidian42-BRAT插件介绍） by 软通达]]

