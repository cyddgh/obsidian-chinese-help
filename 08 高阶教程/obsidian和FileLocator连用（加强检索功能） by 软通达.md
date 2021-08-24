---
title: 
uid: 202108241451
aliases: []
tags: []
from: 
---
本文受到Boninall撰写的“FileLocator （和 Listary）和 Obsidian 联用（需要 FileMenu Tools）”（https://github.com/obsidianzh/forum/discussions/29 ）启发，并根据本人的体验进行了一定程度的再加工和演绎。同时，本文的改进部分得到了蚕子所编写的quicker动作帮助，达到了简化相关步骤的目的。

# 连用的目的
使用FileLocator对ob文档库进行高效检索，FileLocator相比于正则表达式会更加友好。即使不使用本连用，也可以单独使用FileLocator提高检索效率。
使用Listary可以快速唤醒检索功能，形成流程的工作流。

# 实现所需要的软件
- FileLocator 
- Listary
- obsidian（需要升级到0.9.22以上版本）
- Quicker（本人的推荐码555-6895，如购买注册后首次付费购买专业版可获赠3个月使用时长）

注意以上3个软件，FileLocator是收费软件，obsidian、Listary和Quicker都可以使用免费版。另外，我认为可以使用wox替代Listary。


# Listary的配置
- 进入Listary的选项页面
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201217225539.png)
- 进入关键字页面进行相关设置
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201217230307.png)
- 设置内容（上图红色框）如下，其中“本例：”代表本例子的设置情况，大家依照自己的情况修改
1. 关键字：这是在Listary引发该检索行为的词语，可随意设置。本例：fob
2. 显示名：随意。本例：Filelocator
3. 描述：随意。本例：用 Filelocator 搜索 OB 的 '{query}'
4. 路径：需要填写你FileLocator软件的路径。本例：C:\Program Files\FileLocator Pro\FileLocatorPro.exe
参数：这是最重要的参数。本例：-s -r -d "D:\OneDrive\Obsidian\obsidian群分享;!D:\OneDrive\Obsidian\obsidian群分享\.trash" -f "*.md" -c "{query}"
其中“D:\OneDrive\Obsidian\obsidian群分享”为你ob库文件夹的决定路径。
- 点击“应用”，点击“确定”。



# Quicker的配置
本节不同于Boninall所述，采用了蚕子的Quicker的动作脚本“当前MD”（https://getquicker.net/sharedaction?code=7d59873a-894d-4283-592d-08d8a0d98be2 ）。
需要将此动作安装到Quicker面板。


# 具体效果
- 激活Listary检索框，输入上面设置的关键字，然后空格，然后输入要检索的内容。本例：fob 别名
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201217231814.png)
- 会弹出检索的结果框
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201217231837.png)
- 在检索结果中唤醒Quicker面板，点击刚刚添加的“当前MD”动作
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201217232028.png)
- obsidian程序就会被唤醒（需要升级0.9.22以上），并跳转到检索结果的卡片上
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201217232350.png)