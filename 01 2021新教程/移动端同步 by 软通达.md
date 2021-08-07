---
title: 
uid: 202107122119
aliases: []
tags: []
from: 
---
[[obsidian移动端（MOC）]]

本文介绍obsidian的同步方式，主要考虑电脑端和移动端之间的同步。本文成文于2021年6月27日，此后相关服务可能有所变化，请自行甄别。所有涉及收费内容，请自行联系各家公司进行咨询。本文是我个人的主观体验，并不成熟。如果有不同意见请在下方留言，我会将有用的评论标星，以供其他读者参考。

#### 有没有官方对ob同步的指南？
有。在ob帮助文件中，目前只有英文版，中文版已经翻译了。可以点击 https://help.obsidian.md/Obsidian/Obsidian+Mobile 进行查看。

#### 有没有全平台、省心的同步方式？
有！且只有obsidian自己的官方同步。ob的官方同步可以实现windows、Mac、iPhone、iPad、Linux、安卓全平台的同步。[[购买obsidian的服务]]
缺点：
1. 官方同步的费用对我来说有点贵。目前的早鸟价格月付是5美元/月，年付是48美元/年。早鸟价便宜了50%。
2. 官方同步虽然有版本控制功能，但相比专业的git、坚果云还是不足。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210627222131.png)

#### windows和ios系统如何相互同步？
如果你的电脑是windows系统，但移动端是iPhone或iPad，除了官方同步，目前只有iCloud同步可以实现。请注意：iCloud是有windows版本的，详见 https://support.apple.com/zh-cn/HT201391 。更多的iCloud问题，可以联系Apple 支持。至于mac和ios的同步使用iCloud就更容易了。ios

#### 安卓系统和电脑端如何同步？
答：安卓手机的同步方式比较多样。主要有以下几种：
1. FolderSync：FolderSync（ https://www.tacit.dk/foldersync ）可以搭配各种云盘，例如坚果云、onedrive。但我使用FolderSync和坚果云时，因为文件过多且坚果云对第三方的API调用时长有限制，导致同步失败。
2. Syncthing：Syncthing（ https://syncthing.net ）是一个免费的、开源软件，群友淳帅二代推荐了一个介绍视频： https://www.bilibili.com/video/BV1mz4y1R7fD 。但因为采用点对点，网络发现如有问题，就无法同步。我个人使用时，手机发热较为严重，且我在校内网使用时，无法连接。这可能是我对这软件了解不多导致。
3. 微力同步：微力同步（ http://www.verysync.com )是一款类似Syncthing软件，大部分软件功能是免费的，只有少部分功能是收费，我认为是可以接受的。

以上三种方法在QQ群中都有人使用，并且使用得不错，我个人使用的是微力同步。以上的优缺点有我个人主观因素，并不成熟，关于同步软件的问题可以在群内交流或者和相应开发者联系。