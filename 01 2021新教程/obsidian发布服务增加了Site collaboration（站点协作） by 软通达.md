---
uid: 20220503195819
aliases: []
---
obsidian官方发布公告，在0.14.8版本（目前还在内测）中增强了publish（发布）功能，具体可见 https://forum.obsidian.md/t/obsidian-release-v0-14-8-insider-build/36901 。其中最令我关注的是Site collaboration（站点协作）功能，本文主要介绍此项。

上一次有感的发布功能增强，还是为站点设置密码。本次的Site collaboration（站点协作），我尚不清楚如何翻译。因为其协作的概念可能和团队软件（石墨文档等）语境下的“协作”是有不同的。简单的说（我目前也就体验了1小时），该功能是让你能授权其他账号，让其他账号能推送文章到你的ob发布站中。

# 实际操作
下文中，购买了ob发布站的使用者，被称为ob站点拥有者。被授权collaboration的使用者，被称为ob站点参与者。按照官方的说法，拥有者为站点付费，而参与者不用付费（`Only the owner needs to pay for the site, collaborators can join for free.`）。
## ob站点拥有者
ob站点拥有者点击“发布更改”按钮。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202205032022216.png)
在“发布更改”页面下，点击“更改网站设置”。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202205032018703.png)
在“网站设置”中“site collaboration”点击Mange。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202205032018825.png)
在新页面，填写入你要邀请的参与者邮箱，该邮箱应该是一个ob账号（我猜测）。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202205032018052.png)
如果你要删除一位参与者，你可以点击删除键。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202205032019037.png)
## ob站点参与者
当你被授与同步后，你的邮箱会收到一封信件。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202205032007673.png)

你在ob中，登陆你的ob账号，然后开启发布插件，点击“发布更改”按钮
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202205032022216.png)

在“Sites shared with you”中就有你能参与的编辑的ob库。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/202205032008331.png)

点击选择后，就可以和ob站点拥有者一样，对站点的内容进行更改。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/202205032009844.png)

值得注意，该操作不会将ob站点的文件下载到本地，需要另外解决如何保持参与者之间的本地ob库都处于最新版本的问题。例如，我是新建了一个空白库，里面没有任何新文件，如果进行推送更改，就相当于删除所有在线内容。

# 个人的话
按我个人的理解，ob的这个Site collaboration功能是让ob站点拥有者能授权其他的ob用户，让其他的ob用户有权限推送更改到自己的站点中。
