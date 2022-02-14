---
uid: 20220214214030
aliases: []
---
# 引言
Auto note mover插件可以根据所设定的条件，自动移动文件到相关文件夹中。

# 插件名片
Auto note mover插件是由farux开发，目前版本是1.0.7。

Github地址： https://github.com/farux/obsidian-auto-note-mover

# 实际操作
在插件设置页面中

Trigger：可以设置是手动触发（Manual），还是自动触动（Automatic），我选择Automatic。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220214214544.png)


Add new rule：可以设置触发的条件
- Folder：如果触发了，将此文件移动到哪个文件夹。
- Tag：如果文档有此标签，则触发移动。
- Title by regex：如果文档标题符合此正则表达式，则触发移动。例如填入“Tag-”，
- 这里扩展一下正则的表达内容

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220214214614.png)

针对“Title by regex”这里展示2个例子。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220214214920.png)


第1行的设置表示，如果文章标题有"Tag-"，则移动到我的标签文件夹中。这种设置大家比较容易理解，好上手。

第3行则是应用了正则表达式（Regex），`.*?\-\d\d\d\d\-`表示只要文中有四位数字，且数字前后有`-`，则移动到“00 文献文件夹”中。

关于正则的部分，我个人也不是很懂，推荐可以阅读一下材料：
- 正则表达式30分钟入门教程 by deerchao，  https://deerchao.cn/tutorials/regex/regex.htm
- https://regex101.com/

正则表达式也是一个高效的工具，但易学难精，大家可以先入门一下，用到时再差手册，或者向懂正则的高手求助。
