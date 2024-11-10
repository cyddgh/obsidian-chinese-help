---
title: 
uid: 202402021728
aliases: 
tags: 
from:
---
今天看到群友的讨论本地图床，我突然思考PicList有没有插件能用上。PicList是图床管理软件[[PicGo]]的增强a版，改善了很多PicGo没有的功能，我已经使用了一段时间，替代了原有的PicGo。下载链接： https://github.com/Kuingsmile/PicList 。

如果对本地图床还不了解，可以看之前的文章：[[使用本地图床优化obsidian的文件管理]]。

首先，我的PicList是比较早的版本（1.x），在插件商城中用“local”检索，看到了一个本地图床插件。

之后，我将PicList升级到2.x版本后，发现软件已经内置了本地图床功能。

上述两者都可以实现本地图床。

# 实际操作
更多基础操作请见之前的文章。EasyWebSvr设置如下：
- 主目录（本地图床位置）：`D:\Attachment`
- 端口：1993
![](https://gitee.com/cyddgi/picture-store/raw/master/img/2024/02/202402021738890.png)

依据上面的设置，PicList中的设置如下
- 设置路径（按上面本地图床位置）：`D:\Attachment`
- 设定自定义域名：`http://127.0.0.1:1993` （注：`http://127.0.0.1`为本地图床，`1993`是上面的端口号）

![](https://gitee.com/cyddgi/picture-store/raw/master/img/2024/02/202402021743510.png)

设置完毕后，在上传中选择本地上传即可。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/2024/02/202402021748135.png)


# 按日期归档
之前设置图床时，图片直接放在一个文件夹中，没有按日期归档，现在感觉不是很妥当。目前使用了PicList中`设置-上传设置-高级重命名`，重命名格式设为`{Y}/{Y}{m}/{filename}`，这样就能按`年/年和月/文件名`储存到图床中，如`2024/202402/202402021752837.png`。

目前的问题：本地图床和阿里云OSS，可以实现。而Gitee虽然在云端上实现了按文件夹分类，但返回的URL却不包含年、月的目录信息。
