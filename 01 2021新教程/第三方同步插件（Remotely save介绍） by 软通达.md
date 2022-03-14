---
uid: 20220303222512
aliases: []
---
# 引言
Remotely save是新的一款obsidian第三方同步插件，之前我也介绍了livesync插件，见[[livesync同步插件介绍 by 软通达]]。它的优点是能依靠S3同类的数据库、Dropbox、webdav和onedrive个人版进行同步。

需要说明的几点：
1. 目前来看，还是官方同步最让人省心。其他同步方法都有一些技术门槛。
2. 请备份好你的数据，我个人（其实插件作者也说了）不保证该插件的安全性，备份才是王道，建议先看[[使用Kopia来备份obsidian by 软通达]]或者[[obsidian和Git连用实现版本控制（obsidian Git插件介绍） by 软通达]]。
3. 我本人只用了Dropbox同步，对其他方法不了解。



# 插件名片
Remotely save插件是由fyears开发。

Github地址：https://github.com/fyears/remotely-save

# 实际操作
## Dropbox同步
需要注意，Dropbox在国内存在严重的网络访问问题。

在插件中Choose service（选择服务）点击Dropbox

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220303223456.png)

点击Revoke Auth旁边的Auth（授权），在弹出的Dropbox中输入你的账号和密码。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220303223621.png)

授权成功后，可以点击Check，检查是否成功连接

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220303223738.png)

成功链接，会在右上角有一个提醒。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220303223810.png)

然后点击侧边栏的图标，或者进行命令模式中启动同步。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220303223846.png)

首次同步会比较久一些，因为这同步是一个个文件单线程上传，我5000多个文件，上传了几个小时。但有人说用oss能快一些。但全部上传完毕后，之后小量的修改，就同步很快了。

在手机端也是如上操作。

另外建议使用此插件同步多终端时，在终端A上修改后，要到终端B修改时，先在终端A上同步，等待同步完成，然后再到终端B上同步，等待终端B同步完成，再进行修改操作。

## S3数据库
### 亚马逊S3数据库
我有尝试申请了Amazon AWS的免费S3服务，但超过了每月免费的调用额度，我也不清楚，但发了扣费邮件了，而且同步到一半就同步不上了。

如果你还想使用本方法，记得仔细阅读插件在github上的说明，特别是需要配置好cors，作者有给具体的例子，拷贝过去就行，见 https://github.com/fyears/remotely-save/blob/master/docs/s3_cors_configure.md 。

### 阿里云等的OSS服务
恐咖兵糖有撰写一篇 [[Obsidian 同步 Remotely Save S3 配置指南 by 恐咖兵糖]] 见 https://www.ftls.xyz/posts/obsidiannote 。

另外ob论坛中的我想做一条咸鱼，也声明成功使用了该插件，见 https://forum-zh.obsidian.md/t/topic/5037 。

我本人没有尝试，但感觉是可行的。


