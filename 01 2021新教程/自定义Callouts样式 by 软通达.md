---
uid: 20220501194602
aliases: []
---
本文主要介绍如何自定义Callouts的样式。成文过程中得到了群友Eleven的帮助，在此表示感谢。

# 官方案例
想要修改Callouts样式，可以参考obsidian官方帮助文档中Use callouts一节下的Customizations： https://help.obsidian.md/How+to/Use+callouts#Customizations 以下为我在上述网站上的截图。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/202205011949434.png)

官方给出的实例代码为：
```css
.callout[data-callout="my-callout-type"] {
    --callout-color: 0, 0, 0;
    --callout-icon: icon-id;
    --callout-icon: '<svg>...custom svg...</svg>';
}
```

# 个人操作
对于CSS修改，我理解不多，以下只给出我自己的方案。
- 在Lucide（ https://lucide.dev ）上寻找相关的Callouts图标的文件名，例如下图中红框圈中的“airplay”。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202205011952659.png)
- 建立一个CSS片段，保存到ob的CSS片段文件夹，该文件夹在库文件下的`.obsidian\snippets`。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202205011954004.png)
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202205012004782.png)
- CSS片段如下
```CSS
.callout[data-callout="democallouts"] {
    --callout-color: 195, 0, 47;
    --callout-icon: airplay
}
```

代码中各片段解释如下：
- democallouts：自定义，你可以自选一个英文或中文词，英文要全部小写。
- 195, 0, 47：自定义，请输入一个RGB的色号。
- airplay：Lucide（ https://lucide.dev ）上找到的图标名。

然后在ob中输入的字符为
```
> [!democallouts]
> 假设1：
> 
```

显示的效果为
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202205012005175.png)

目前的不足：我对于官网帮助中的自定义片段（`--callout-icon: '<svg>...custom svg...</svg>';`）不是很了解，这可能是可以自定义一个本地的或其他地址的图标，但我没有进一步学习了。

