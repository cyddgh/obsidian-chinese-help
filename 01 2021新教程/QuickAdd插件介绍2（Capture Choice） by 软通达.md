---
title: 
uid: 202107272031
aliases: []
tags: []
from: 
---
# 摘要
本文介绍了QuickAdd插件的剪藏选项（Capture Choice），可以通过一个输入框进行快速输入。

# 引言
之前已经介绍了QuickAdd插件的模板选项（Template Choice），本文将继续介绍第2种模式剪藏选项（Capture Choice）。作者是如此介绍这功能的“Quick capture anything, anywhere.”。

另外，近期Bon在知乎专栏中也介绍了他使用QuickAdd的心得，可见 https://zhuanlan.zhihu.com/p/386885976 。他在文中将Capture翻译为“剪藏”，我个人的理解更偏向“捕获”（捕获输入框中的信息，做成卡片）。

相比于Bon撰写的心得文章，本文会更像是对插件开发者给出范例的中文说明（ https://github.com/chhoumann/quickadd/blob/master/docs/Choices/CaptureChoice.md ）。

# 插件名片
QuickAdd插件是由chhoumann开发，目前版本是0.3.4。但我个人使用非常不顺，这教程写得我崩溃，怀疑有很多bug，或者和我其他插件冲突了。下面演示的版本是0.2.16。

Github地址： https://github.com/chhoumann/quickadd
蓝奏云地址： https://wws.lanzoui.com/i8Hfqr0b18h

# 实际操作
## 案例来源
本案例来自插件开发者的给出的范例： https://github.com/chhoumann/quickadd/blob/master/docs/Choices/CaptureChoice.md 。但可能有所改变。
该案例是演示通过剪藏选项，快速在日记卡片中输入今日的日程信息。

## 建立日记
在设置-核心插件中打开日记插件。做以下设置（可以和我不同，我只是用于演示）

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210711201853.png)

具体的日记模板如下

```
# 今日要做的三件事
1. 

# 今天活动

```

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210711202015.png)

## 设置Quickadd插件的剪藏选项（Capture Choice）
添加一项Capture动作

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210711202122.png)

点击齿轮按钮，进入配置。如果常用，建议也点亮闪电按钮。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210711202229.png)

具体的设置选项，Bon已经在讲述很清楚了，我就不再赘述。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210706213423.png)

（上图来自于Bon的文章：https://zhuanlan.zhihu.com/p/386885976  ）

因为我的日记文件位于根目录下的“日记"文件夹中，每日日记的文件名显示是”2021-07-11“。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210711202654.png)

因此我在File Name一栏输入`日记/{{DATE:gggg-MM-DD}}.md`。我没有选`Create file if it doesn't exist`，相当于默认，每天开打ob后我都会先生成日记文件。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210711203405.png)

在`Insert after`（在某些之后插入）一栏，我输入`# 今天活动`。并开打`Insert at end of section`（插入在此节的最后），因为时间任务是依次往下的。

最后打开`Capture format`，并在下方输入`- {{DATE:HH:mm}} {{VALUE}}`。其中`{{DATE:HH:mm}}`是时间，`{{VALUE}}`是你输入框内的值（文字信息）。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210711203908.png)

## 从命令模式运行剪藏选项（Capture Choice）

按Ctrl+P进入命令模式，检索quickadd，如果刚刚有将这选项的闪电标志点亮，该命令就会直接出现在命令模式中。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210711205312.png)

如果没有，则需要点击`Quickadd: Run Quickadd`，在所有的Quickadd命令中寻找改命令，找到后点击。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210711205443.png)

然后会弹出一个输入框，我输入“写Quickadd的文章”，按回车完成输入。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210711205531.png)

最后在日记文档中，就会出现如下结果

```
# 今日要做的三件事
1. 

# 今天活动

- 20:51 测试
- 20:55 写Quickadd的文章
```

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210711205639.png)

其中`- 20:51 测试`是我之前测试的结果，`- 20:55 写Quickadd的文章`是我刚刚输入的结果。本文到此也就要结束了，最后我们再输入“结束Quickadd文章的写作”，就会出现下图。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210711205812.png)