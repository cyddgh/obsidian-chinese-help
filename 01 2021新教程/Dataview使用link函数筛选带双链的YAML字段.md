---
title: 
uid: 202201211428
aliases: []
tags: []
from: 
---
首先感谢宏沉一笑的帮助。

# 背景
因为我在使用Breadcrumbs插件，卡片中增加了许多yaml字段，想用Dataview进行筛选总结。

# 实例
卡片“A”中，含有`“CardType:: [[材料-网站]]”`。

筛选语句
````
```dataview
list
from ""
where contains(CardType, link("材料-网站"))
```
````

注意，该语句使用`where contains(CardType, "[[材料-网站]]")`是无法筛选的





