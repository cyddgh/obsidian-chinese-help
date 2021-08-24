---
title: 
uid: 202107051942
aliases: []
tags: []
from: 
---
# 摘要
本文介绍了Enhancing mindmap插件，其能在obsidian中创建思维导图。

# 引言
思维导图是大家耳熟能详的一类软件，以xmind、MindManager为代表。本文介绍的Enhancing mindmap插件能让obsidian承担大部分思维导图的工作。本文撰写于此插件发布3小时内，如有不足之处，请大家留言补充。
因为本人不怎么使用思维导图，所以介绍和用词不一定准确。我之所以如此快速（兴奋）地撰写本文，是因为这个插件能在思维导图模式（浏览模式）下，通过快捷键进行编辑操作。ob之前的思维导图插件似乎没有实现，这可谓是一大突破。

# 插件名片
Enhancing mindmap插件是由MarkMindLtd开发的一款插件，在今天刚刚发布在github，目前版本0.0.1。
Github地址： https://github.com/MarkMindCkm/obsidian-enhancing-mindmap
蓝奏云地址： https://wws.lanzoui.com/ijSeUr1br7i


![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210705200530.png)

# 实际操作
## 官方指导
https://github.com/MarkMindLtd/obsidian-enhancing-mindmap

##  yaml中的激活字段
开启该插件后，在yaml（md文档最开头）中输入以下字段，就能将此卡片变成看板。这操作类似于看板插件。

```
---
mindmap-plugin: basic
---
```

## 在md和思维导图模式间切换
点击卡片右上角的菜单按钮，点击“打开为思维导图”将md卡片变成思维导图。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210705194950.png)

## 思维导图模式下的操作

| 操作（官方英文）                  | 按键                  | 操作（我给的翻译） |
|---------------------------|---------------------|-----------|
| New Mind Map              | Ctrl/Cmd+P          | 新的导图      |
| New child node            | Tab                 | 新的子节点     |
| New brother node          | enter               | 新的兄弟节点    |
| Delete node               | Delete              | 删除节点      |
| edit node                 | space/dblclick node | 编辑节点      |
| Undo                      | Ctrl/Cmd+Z          | 取消        |
| Redo                      | Ctrl/Cmd+Y          | 重做        |
| quit edit node            | tab                 | 离开编辑模式    |
| expand node               | Ctrl/Cmd + /        | 展开节点      |
| collapse node             | Ctrl/Cmd + /        | 收缩节点      |
| move node to another node | drag and drop node  | 移动节点到另一处  |
| tab node                  | up/down/left/right  | 选择节点      |


