---
title: 
uid: 202107282217
aliases: []
tags: []
from: 
---
# 摘要
本文介绍了Git软件和其教程，详细说明了如何使用obsidian Git插件完成obsidian和git连用。

# Git的介绍
通俗来讲，Git是一种版本控制软件。我们需要了解Git和Github类网站（如Github、Gitee等）的区别：
- Git是一款本地运行的软件，如QQ。Github或Gitee是一个在线网站，如腾讯网。
- 运行Git后有形成一系列版本文件，你可以将其提交到Github或Gitee等网站（类似于仓库）。

如果你需要更加明确这概念可以前往：
- 菜鸟网：https://www.runoob.com/git/git-tutorial.html
- 廖雪峰：https://www.liaoxuefeng.com/wiki/896043488029600/
本文不对git做更多的知识普及，主要集中在git和obsidian的连用，默认读者已经能熟练使用git。根据我学习的经验，选择上述任一学习资料，通过1-2小时学习即可入门。

此外，因为git默认的界面不是很适合普通用户，我使用Sourcetree（一种Git的可视化软件）来进行演示。此软件的安装在百度中也有很多的文章解释，特别是廖雪峰老师在教程中也有详细介绍（https://www.liaoxuefeng.com/wiki/896043488029600/1317161920364578 ）我也不再论述。

# 实际操作
为了演示方便，我新建了一个ob库，名称为“git测试”。
## 在库文件内建立Git同步文件夹
- 在SourceTree中点击“Create”
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210104230349.png)
- 选择好我们ob库的文件夹（我的库名称是“git测试”，你的会有不同），点击确认
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210104230451.png)
- 点击创建
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210104230649.png)
- 点击“是”
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210104230721.png)

## 安装Obsidian Git插件
- 我们按下图所示安装ob内的第三方插件“Obsidian Git”。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210104230112.png)
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210104230153.png)
- 打开该插件，并前往设置
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210104231045.png)
- 将第一项（多久备份一次）的值设为1，这表示每1分钟备份一次，大家可以依照自己的喜好设置。另外，0表示不进行git备份。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210104231130.png)
- 其他选项不必更改。如有兴趣可自行翻译后修改。

更多关于该插件的信息可以前往作者的github页面了解（https://github.com/denolehov/obsidian-git ）。
需要注意的是，该插件默认你已经安装了git，且ob库中已有git软件所产生的“.git”的文件夹（This plugin assumes you have existing git repository initialized locally and credentials are setup.）。所以上述的步骤顺序不要颠倒。

# Obsidian Git插件的效果
在文档中我先输入了第一行文字“落山鸡在测试Obsidian Git插件的效果，这是第一行。 ”。等待1分钟后，我再输入第二行文字“obsidian的QQ交流群：774176839”。出现了以下效果。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210104231832.png)

在Sourcetree中可以看到有两个备份，选择最新的版本，在右下角处可以看到版本控制的信息。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210104232053.png)


# 本文还有待改进的地方
本人对git和github的使用不是很熟悉，如果读者对上述流程有所改进建议，还请留言。本文可能还欠缺的方面有：
- 如何将本地的文件传输到github上。我认为你学习完菜鸟网或者廖雪峰的课程后，应该已经有能力完成。
- 没有演示版本回滚、怎么追踪版本，没有体现版本控制的精髓。理由同上。
- 没有使用Git自身软件。我本人也不太擅长使用Git的Bash或GUI界面，所以借助了SourceTree这款免费的、网上教程很多的Git可视化软件。大家有什么好用的、免费的Git可视化软件也请推荐一下，我的SourceTree在Win10上有时很卡，之前尝试了GitKraken，很好用，但收费了。
