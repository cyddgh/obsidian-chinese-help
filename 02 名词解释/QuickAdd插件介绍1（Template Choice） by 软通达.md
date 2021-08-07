---
title: 
uid: 202107272030
aliases: []
tags: []
from: 
---
# 摘要
本文介绍了QuickAdd插件的模板选项（Template Choice），可以快速制作一些卡片。

# 引言
obsidian本身有模板功能（核心插件），也有一个第三方插件（Templater）提供模板插入，今天介绍的Quickadd也有相同的功能。它们三者互相有所区别，大家在使用中可以体会看看。正如这开发者说的：模板选项不意味取代Templater插件或核心插件，而是对它们的加强。
> The template choice type is not meant to be a replacement for Templater or core Templates. It's meant to augment them. From https://github.com/chhoumann/quickadd/blob/master/docs/Choices/TemplateChoice.md 

# 插件名片
QuickAdd插件是由chhoumann开发，目前版本是0.3.4。但我个人使用非常不顺，这教程写得我崩溃，怀疑有很多bug，或者和我其他插件冲突了。下面演示的版本是0.2.16。

Github地址： https://github.com/chhoumann/quickadd
蓝奏云地址： https://wws.lanzoui.com/i8Hfqr0b18h

该插件有4种模式：
- Template Choice - A powerful way to insert templates into your vault.
- Capture Choice - Quick capture anything, anywhere.
- Macro Choice - Macros to augment your workflow. Do more, faster.
- Multi Choice - Organize your choices in folders.

本文主要介绍第一种模式：模板选项（Template Choice），提供一种有力的方式将模板插入到你的文档中。



# 实际操作
## 开发者说明
开发者给出了Template Choice具体的说明，位置在 https://github.com/chhoumann/quickadd/blob/master/docs/Choices/TemplateChoice.md

## 创建一个Template Choice
先在第三方插件中，启动Quickad插件。
进入Quickadd设置页，Name一栏输入“测试Template Choice”（名字任取），下拉栏选“Template Choice”，然后点击“Add Choice”
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210704210359.png)

点亮闪电按钮，可以让我们更好在命令模式下找到它。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210704214345.png)


点击小齿轮按钮，开始进行配置。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210704210751.png)

## 配置Template Choice

先上一副总图
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210704211843.png)

以下操作如果太难，可以只看Template Path和Create in folder就行。下面标注“没弄懂”的部分可能是因为插件版本的原因，现在这版插件的bug还是太多了，我主库和演示库的效果都还存在不同，我也不清楚是为什么。

1. Template Path：输入你模板的位置，注意以.md结尾，这是唯一的必填项。我讲模板放在库目录下的模板文件夹，文件名是英语学习，所以输入“模板/英语学习.md”。注：在我的演示库，模板是手动输入，但在我的主库，模板是下拉选择，不清楚为什么会有这样的差异。
2. File Name Format：卡片名称格式。如果不开启，就是当时会弹出输入框。如果开启，可以在下方的File name中输入一些预定设置，例如输入`{{DATE}}`，则显示今天的日期（2021-07-04）；输入`{{NAME}}`，则弹出输入框，让你添加信息，并作为卡片名称。注意如果开启后，在File name没有`{{NAME}}`字段，则自动创建卡片，不需要人为输入。
3. Create in folder：卡片是否创建在特定的文件夹（可以有多个，也可以不开启）。我选择在“quickadd添加”文件夹，如下图。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210704212851.png)
注意选择后需要点击Add按钮，才能添加成功。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210704213419.png)


4. Append link：没弄懂。我理解的是，在当前页面中留下新卡片的双链。
5. Increment file name：没弄懂。我理解的是，如果存在一张卡片名为“obsidian”，当再次新建一张“obsidian”卡片时，会自动命名为“obsidian1”。
6. Open：没弄懂。我理解是会自动打开新的卡片。

## 运行Template Choice

在obsidian，进入命令模式（Ctrl+P），选择Quickadd。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210704214453.png)

进入Quickadd页面，这里会显示所有的quickadd命令，我们接着点击“测试Template Choice”
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210704214557.png)

然后会弹出一个界面，让我们输入这新卡的名称，然后按回车确认。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210704214700.png)

然后就会创建一张根据模板而来的卡片。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210704214736.png)

# 个人的话
上面的演示可能很枯燥，和其他实现模板的功能很类似。这可能是因为是介绍基本功能。下面列举一些我认为好玩的地方：
1. 可以自定义多个文件夹：这样就可以快速建立卡片到不同的文件夹中。例如词组到一个文件夹，单词到一个文件夹，前后缀到一个文件夹。
2. 卡片名可以自定义。自定义这块应该还很多可以设置，但我没有细看。可以去作者说明中看看。

