---
uid: 20221002100223
aliases: []
---
# 引言
obsdian-zotero插件是aidenlx刚刚开发的一款插件，可以方便ob和zotero的连用。（我理解的）其重要功能是，可以在ob中读取zotero数据库，并且可以读取zotero中PDF所做的笔记，并进行页面跳转。具体效果如下。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/202210021007146.png)



# 插件名片

obsdian-zotero插件是由aidenlx开发，目前版本0.2。

Github地址： https://github.com/aidenlx/obsidian-zotero-plugin

但需要注意几点：
- 该插件22年10月1日才刚发布，功能可能还未调试完全，特别是开发者还没写readme，所以本文对软件的理解仅供参考，如有问题请直接联系插件开发者。
- 目前我只在win上运行成功，但在mac上也听说能正常使用。
- zotero可能要升级到6.0版本才能使用。
- 该插件的安装有一些注意事项，可能有一些门槛。


我已经将我在用的`better-sqlite3.node`文件连同此插件打包到一个压缩包中，下载地址：https://wwb.lanzouv.com/ihXVf0ctzsfa 。

# 实际操作

## 安装前事项
- 该插件的安装需要替换`.obsidian`里的`better-sqlite3.node`文件，并且替换后打开ob时会触发一次索引。
- zotero中需要安装Better BibTex插件并开启。

## 配置
第1、2行的文件夹，请指向你zotero文件夹里的文件。
第3行是你ob库中文件夹，文献卡片会创建在这文件夹中。
其他参数我保持不变。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202210021054930.png)

## 运行
按Ctrl+P进行命令模式，寻找该插件的命令
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202210021057228.png)

点击 open quick switcher for literature notes会读取你的zotero库，点击文献后，会在ob中新建一个文献卡片。（目前检索主要是标题检索优先）
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202210021101633.png)

点选文献后，就会生成一张卡片，再点击open zotero annotation side panel就能读取zotero所做的笔记，点击“page 1”可以跳转。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/202210021007146.png)