---
title: 
uid: 202112131136
aliases: []
tags: []
from: 
---
# 引言
livesync是obsidian中的一款第三方同步插件，借助CouchDB（可以免费使用IBM，或者自建）数据库来同步多终端上的ob数据。开发者称可以运行在CouchDB。本文主要是依据开发者本人自述（ https://github.com/vrtmrz/obsidian-livesync/blob/main/docs/setup_cloudant.md ）进行配置，我个人对具体机制不是很了解。但通过开发者的文档配置成功，并且在win和安卓上同步成功。

同步前后，我使用git软件对ob库进行监控，没有发现文本被改动的情况，除了Booknote插件所产生的一些xml格式文件。这说明该同步插件对非md的文本文件可能存在一些兼容问题，大家最好配合git使用。

另外，说句题外话，最近ob的同步功能增强了批量恢复，有购买同步服务的使用者可以去看看。

# 插件名片
livesync插件是由vrtmrz开发的一款插件，目前版本0.1.25。

Github地址： https://github.com/vrtmrz/obsidian-livesync

# 实际操作
参照： https://github.com/vrtmrz/obsidian-livesync/blob/main/docs/setup_cloudant.md

本操作不是很详细，建议对照英文原文操作（主要是英文的说明已经很不错的，只是有个别地方可能有些跳跃）。

## IBM部分
注册账号： https://cloud.ibm.com/registration

在目录中查找"Cloudant"的项目： https://cloud.ibm.com/catalog

"Cloudant"的项目页面： https://www.ibm.com/cn-zh/cloud/free

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211213115427.png)


此处需要选
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211213115527.png)

双击Cloudant-bl
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211213115650.png)

复制"External endpoint (preferred)"，需要填写到ob中的插件设置中。

开启CORS option
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211213120156.png)

然后创建Database，Database name可以自定义创建，后续需要填写到ob的插件配置中。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211213120258.png)


创建服务凭证 "Service credentials".
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211213120647.png)

弹出的创建直接确认就行。

创建后，点击箭头，记录下方的username和password。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211213121003.png)



## ob中的插件设置
在ob中开启本插件，然后在设置页面填写入IBM设置过程中的“External endpoint (preferred)”、username、password和“Database name”。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211214230619.png)

输入上述信息后，在侧边栏点击“Replicate”按钮（或者通过命令模式）就可以同步了。

我遇到过点击后无法同步的情况，提示我需要查看日记信息。我进入插件配置，把一些警告点击确认后，就恢复了。



![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211214230811.png)

