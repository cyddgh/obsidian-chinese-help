0.9.16版本obsidian之后就可以使用别名（aliases）功能，本文会先介绍我个人对此功能的理解，最后附上obsidian官方的部分介绍。

# 别名功能的介绍
别名可以视为多词一义的现象，即多个不同的名词指向同一个含义。当你笔记标题可以用多个名词来命名时，你可能就需要用到别名这个功能。
例如，一般情况下英文、英语和English所指向的含义是相同的。你会讲英文/英语/English给人传达的意思是一样的。
又例如，卢曼卡片、知识卡片、卡片盒、zk笔记法、滑箱笔记法等等，也都可以视为多词一义。

# 我个人使用别名的场景
我在使用ob软件中，比较喜欢以“中文名（英文名）”为标题给卡片明明，例如“生态学（ecology）”，但这样就可能导致ob中“提到当前标题”的功能失去作用，因为材料中很少会出现“生态学（ecology）”，一般中文材料只会出现“生态学”，英文材料只会出现“ecology”。而别名功能的出现，就可以很好解决这个问题。

# 如何在ob中使用别名
我不了解是否有其他的方式，目前我就用了这最基本的方式，本文已经更新到ob教程“如何使用别名（aliases）”。
在笔记的开头输入以下格式
```
---
aliases: [,]
---
```

需要注意的一件事情是，
- 别名前后都有符号（---），ob称其为FrontMatter，而在md中是一种YAML语法，大家感兴趣可以去菜鸟网学习（ https://www.runoob.com/w3cnote/yaml-intro.html ）。
- 别名所用的符号都是英文，如果输成中文符号就无法启动别名功能。

# 范例
在ob教程中“如何使用别名（aliases）”一节，一开始是没有任何一篇文档显示在“提到当前标题”一栏中。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201203191942.png)

但当输入别名后，在“提到当前标题”一栏就出现了有关别名（“双链”、“卢曼”）的内容了。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201203192123.png)


# 官网对别名的介绍
官网的原文（https://forum.obsidian.md/t/obsidian-release-v0-9-16/8795）：
> You can now specify aliases in front matter. These will then show up in the [[ link suggestion, and auto-complete to the correct file. They will also be picked up in unlinked mentions. For example: aliases: [AI, Artificial Intelligence]. Add double quotes around your alias if it contains special characters.

官网的范例:
```
---
aliases: [AI, Artificial Intelligence]
---
```

