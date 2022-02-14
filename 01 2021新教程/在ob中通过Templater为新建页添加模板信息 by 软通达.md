---
title: 
uid: 202202050647
aliases: []
tags: []
from: 
---

# 引言
我有一个需求，看英文文章时，对不懂的单词做双链，需要在新建页面提供一个uid方便以后anki调整。换句话说，有没有某个插件能给每个新建的页面都加上一个模板，例如每个新页面（包括ctrl+点击）都有一个如下的yaml

```
---
uid: 202108151016
---
```

默认的[[模板（核心插件]]和[[ZK卡片（核心插件）]]都无法满足我的需求。感谢群友的帮助，提出可以使用[[Templater（模板增强插件）]]来实现这功能。

# 实际操作
安装并启动[[Templater（模板增强插件）]]（现在下载量居然已经11万了）。

打开Trigger Templater on new file  creation。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220205065535.png)

下方就会出现Floder Templates，在Folder（文件夹）中输入`/`表示根目录，即ob全局新建的笔记都包括，也可以只指定某个文件夹。在Template（模板）中指定你的模板。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220205065701.png)

这样就配置完成了。

相关的模板如下
```
---
uid: <% tp.date.now("YYYYMMDDHHmmss") %>
aliases: []
---
<% tp.file.cursor() %>
```

因为还用了`<% tp.file.cursor() %>`语句，所以还需要在Templater打开Automatic jump to cursor

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220205072153.png)