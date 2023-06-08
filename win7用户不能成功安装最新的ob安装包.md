---
uid: 20230515101553
aliases: []
---
摘要：因为最新版本的Electron不支持Windows7，所以win7上的ob用户不能使用1.2.7的obsidian安装包，只能安装1.1.16安装包，然后通过接受内部更新升级ob版本。

首先要明确一个概念，obsidian版本在“关于”中有两个，一个是当前版本，一个是安装程序版本。“安装程序版本”是指当前ob安装包的版本，“当前版本”是最新的ob版本，因为ob的升级不一定要通过重新安装安装包，可通过内部接受推送完成升级（所以不用每次ob升级，都在群里求安装包）。但当ob更新其底层框架[[Electron]]时，如果为了新功能或者功能优化，需要从官网下载ob安装包，进行安装。

最近obsidian版本从1.1.16升级到了1.2.7，这次升级同时升级了Electron版本。

然而，新版本的Electron框架停止了对Windows7的支持，导致1.2.7以后的ob安装包，将无法在windows7系统上成功安装，会弹出报错“无法定位程序输入点DiscardVirtualMemory于动态链接库KERNEL32.dll上。” （来自群友的反馈 ）

![](https://gitee.com/cyddgi/picture-store/raw/master/img/202305151039870.png)

类似的报错反馈已经出现在其他软件上，例如 CSDN这则帖子： https://blog.csdn.net/weixin_41913973/article/details/129624908

根据ob英文论坛的帖子“Windows 7 support silently dropped?”（ https://forum.obsidian.md/t/windows-7-support-silently-dropped/59341 ），WhiteNoise（OBSIDIAN TEAM）给出的一种解决方式如下：
- 从Github上下载1.1.16的安装包： https://github.com/obsidianmd/obsidian-releases/releases/tag/v1.1.16
- 之后仅更新ob核心，而不更新electron版本。这应该是指在设置-关于-检测更新。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/202305151024333.png)


> You can download and reinstall Obsidian 1.1.6 from https://github.com/obsidianmd/obsidian-releases/releases 7 and rely on the internal update method (it does not update electron but just the core app).
> As long as it works, fine, but we are not going it accept bug reports against this version and at some point something will break. When that day comes, please don’t post another rant here. We got the memo already.
> 你可以从 https://github.com/obsidianmd/Obsidian-releases/releases 6下载并重新安装黑曜石1.1.6，并依靠内部更新方法(它不更新电子版，只更新核心应用程序)。只要它工作，好，但我们不打算它接受错误报告对这个版本，并在某一点上会打破。当那一天到来的时候，请不要再在这里发表任何言论。我们已经收到备忘录了。
> 英文来自WhiteNoise，中文为机器翻译。