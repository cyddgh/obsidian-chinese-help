转自[[落山鸡]]写的微信文章 https://mp.weixin.qq.com/s/LItcevoqduIpkA5PYcNqWQ

本文主要介绍了如何开启obsidian第三方插件、如何手动安装插件和插件使用的一些注意事项。目前还不完善，未来可能继续更新。
提醒：注意插件的安全性。ob的插件应该是使用JavaScript代码书写，有能力的使用者可以自行审视插件是否包含恶意代码，或者等待官方后续支持。

# API插件的开启和安装
目前ob似乎还没通过插件审核，需要使用第三方插件。
将ob升级到0.9.10版本
- 前往Third-party plugin关闭safe mode（安全模式，请看下方的使用警告）。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201104112034.png)

- 关闭safe mode时会有弹窗，选择Turn off safe mode
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201104112230.png)

- 关闭安装模式后，就会出现Community plugins（社区插件）
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201104112342.png)

- 点击Browse（浏览），就可以开始浏览和安装相关插件。如果无法浏览，可能是网络问题，请见下一章节。

- 点击图中的install，就可以安装改插件，有些插件安装完成后需要重启才能生效。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201104112625.png)

- 重启之后，前往Third-party plugin将要启动的插件勾选上
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201104113326.png)

# 手动安装插件
如果大家遇到网络问题，无法从ob内置的商城下载，可以使用手动安装。
大家可以前往Github（如 https://github.com/search?q=obsidian+plugin ）。
将下载后的插件放在库文件夹（下图的库文件夹是obsidian群分享）下的“.obsidian”文件夹，如下图
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201104113556.png)

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201104113647.png)

然后重启，其他请参加上一章节。

我自己打包了图中的3款插件，如果感兴趣可以下载（ https://cowtransfer.com/s/e734433bb5ac44 ，有效期7天，只能供100次下载）


# 插件使用警告
1. 注意一些插件可能导致文档丢失，特别是涉及文档读写。例如有群友反馈，安装完Reading Time后，文档丢失。请注意文档的版本保存。
2. 一些插件可能会有恶意代码，对于来历不明的插件请保持谨慎。

# 后序
期待大家在文后分享一些有趣的插件（本人不对文中和后续插件的安全性负责），请使用者自行分辨。手动安装有一定技术门槛，如果操作不成功，可以等后续官方的支持。