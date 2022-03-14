---
uid: 20220226210224
aliases: []
---
# 引言
obsidian的插件下载大致可分为两种，第一种是从ob软件内的官方渠道下载，第二种则是通过Github等渠道下载后再手动安装。一般而言，插件都是先在github上进行发布，然后等待ob官方审核，才能上架。对于想要提前体验插件的用户需要从github上下载。此外，一些插件可能因为各种原因无法上线ob官方的渠道而仅在github上提供安装，可能包括源代码审核困难（例如[[ZH增强编辑插件]]）、版权敏感（例如[[Booknote插件]]）。因此，从github上下载插件对于ob使用者是有必要学习的一项技能。

今天介绍的[[obsidian42 Brat(安装测试版插件)]]则能方便大家对从github上下载的插件进行快速安装和管理。目前，许多插件都支持了这种安装模式，例如[[Bartender插件]]。

请注意，如果访问github存在网络困难，可能该插件无法生效。

# 插件名片
obsidian42 BRAT插件是由[[TfTHacker]]开发，目前版本是0.6.31。

Github地址：https://github.com/TfTHacker/obsidian42-brat

值得说明的一点是，TfTHacker是ob插件的开发大神，其开发了4个以obsidian42的开头的ob插件，大家可以去体验看看。我之前已经介绍了[[跳转到指定日期的日记Daily Note（obsidian42 Jump to date插件介绍） by 软通达]]。

# 实际操作
本文以目前还未上架的Bartender插件为例（这个插件也挺有意思，推荐大家去看看）。

进入obsidian42 BRAT插件内，在Beta plugin list一栏中，点击Add beta plugin。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220226211712.png)

Bartender插件的github地址为`https://github.com/nothingislost/obsidian-bartender`。我们在弹出的窗口输入`https://github.com/`后的`nothingislost/obsidian-bartender`，然后点击Add plugin。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220226211854.png)

在下方出现该插件后，就是成功安装上该插件了。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220226211935.png)

然后到插件列表启动该插件就可以了。

下面贴上bartender作者写的安装说明。

1.  Install the BRAT plugin
    1.  Open `Settings` -> `Community Plugins`
    2.  Disable safe mode, if enabled
    3.  _Browse_, and search for "BRAT"
    4.  Install the latest version of **Obsidian 42 - BRAT**
2.  Open BRAT settings (`Settings` -> `Obsidian 42 - BRAT`)
    1.  Scroll to the `Beta Plugin List` section
    2.  `Add Beta Plugin`
    3.  Specify this repository: `nothingislost/obsidian-bartender`
3.  Enable the `Bartender` plugin (`Settings` -> `Community Plugins`)