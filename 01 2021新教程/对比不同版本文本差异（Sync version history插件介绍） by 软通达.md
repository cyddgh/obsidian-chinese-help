---
uid: 20220314210608
aliases: []
---
# 引言
对比不同版本间文本的差异是一项急需且常用的功能。一般纯文本的比较工具是git，除了git外，Beyond Compare等工具也能提供更为高级的对比。
Sync version history则可以较好实现git中的对比功能（diff），对obsidian库中的文本进行对比。

# 插件名片
Sync version history插件是由kometenstaub开发，目前版本1.2.0。

Github地址： https://github.com/kometenstaub/obsidian-sync-version-history

# 实际操作
需要先了解的信息：
1. Sync version history插件需要搭配ob核心插件中的[[同步（sync核心插件）]]或者[[文件恢复（File Recovery，核心插件）]]。
2. [[文件恢复（File Recovery，核心插件）]]可以参考往期推文[[obsidian内置文件恢复（File Recovery功能介绍） by 软通达]]。
3. [[文件恢复（File Recovery，核心插件）]]所备份的镜像仅限本机，且有一定时效性（以你设置为主）。[[同步（sync核心插件）]]的数据则可以联机。

安装并启动插件。因为我没有同步服务，所以只演示文件恢复的模式。

进入Crtl+P进入命令模式，进入“Version history diff:Show File Recovery diff view for active file”（注意不要进入sync的选项，如果没有同步如何就会是一个空白弹窗）。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220314211549.png)

然后就会弹出类似git的窗口
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220314211742.png)

建议可以在文件恢复中，将快照的保存时长设置长一些，例如30天。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220314211831.png)
