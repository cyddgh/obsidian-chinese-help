---
title: 
uid: 202506222139
aliases: []
tags: []
from: 
---
# 摘要
本文介绍了如何用Doc2x将PDF格式的文件转换为Markdown格式，放入obsidian中，并介绍了Linter插件进行格式优化。如果有隐私考虑，也可以用文末所提及的其他软件，进行本地化的转化和翻译。

# 引言
在日常的学习和工作中，我常常要阅读PDF格式的学术论文。进入25年，知识库的出现，让更多的AI软件可以阅读本地的知识库来回答问题。因此，我就尝试将论文从PDF格式转为Markdown格式放入obsidian中进行阅读，并以此构建本地的知识库，增强AI的专业能力。本文主要介绍相关的工作流程。
# 工作流程
首先，我用的PDF转Markdown软件是Doc2x（链接： https://doc2x.noedgeai.com?inviteCode=DN9S5V ，邀请码：DN9S5V）。目前我已经付费了3个月。免费版，每天签到可以转换10页PDF；最基础的付费版本，8.9元，可以转换600页，并有翻译功能，大概处理1页PDF是0.015元。

将下载好的PDF拖入下方页面，或者上传相关文件。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/2025/202506/20250622214657972.png)

一般而言，为了省钱，我的页码不包括参考文献部分，另外开启翻译，但不翻译代码、表格、图片和参考文献。翻译功能还是有一定必要，特别是对于一些刚入门的科研新生可以让他们快速阅读SCI文献。

![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/2025/202506/20250622214826808.png)

点击处理后，等待完成，在页面的左边，选择翻译后的文件，导出，格式中的公式符我一般使用`$`，图片务必选择本地图片，如果是在线图片大概1个月后就失效了。

![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/2025/202506/20250622215054415.png)

下载得到的是一个zip压缩文件，将压缩文件放入你的obsidian库中。我这里专门为文献阅读设置了一个库，附件专门放在`Attachment`文件夹中（注意按下图设置好相关的目录），翻译后的Markdown文件放在你想要的文件夹中。

![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/2025/202506/20250622215417075.png)

因为Doc2x的md文件中的图片引用格式与ob不同，需要再用[[Linter（格式刷插件）]]进行一下正则替换，在Linter的设置页中，找到“自定义”页面，然后，增加一个正则表达，分别输入`\[([^\]]+)\]\(images\/[^\)]+\)`、`gm`、`[[$1]] `（如下图，正则表达我也不懂，感谢热心群友提供的帮助，如果你有更好的代码可以自行替换）。
![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/2025/202506/20250622215557957.png)

然后Crtl+P进行命令模式，运行`Linter：格式化当前文件`，即可修复图片引用

![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/2025/202506/20250622215846203.png)

最终的效果图如下

![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/2025/202506/20250622220020522.png)


# 其他值得讨论的问题
本文还有许多值得讨论和优化的地方，大家可在公众号内留言讨论。
## PDF转化为Markdown格式的方法
除了Doc2x外，目前的还有许多的软件，例如minerU、markitdown、，但我尝试后效果不如Doc2x，而且Doc2x还包括了翻译的费用。

## Markdown的双语翻译方法
我目前也在关注md格式的双语翻译。沉浸式翻译确实好用，但对于md文件来说还缺乏优化。目前关注的一些软件有DocTranslator（早期用过，很难受）、AiNiee（近期刚关注的）。

上述的软件搭配上本地的大语言模型，可以使得本文的流程完全本地化。

## 如何在ob中对md文件进行批注
目前，我是使用了HiNote插件（ https://github.com/CatMuse/HiNote ），只能进行了很简单的批注，目前没看到相关的插件。
