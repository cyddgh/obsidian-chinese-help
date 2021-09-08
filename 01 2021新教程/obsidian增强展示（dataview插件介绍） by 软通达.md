---
title: 
uid: 202107220937
aliases: []
tags: []
from: 
---
[[软通达]]
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210316083056.jpg)
图源：群友Vast & Hazy

# 摘要
本文介绍了dataview插件，能检索卡片中的yaml字段，加上检索条件限定，最后以list、table或task形式展示。该插件属于高级插件，初学者可以延后学习。

# 个人的话
本文介绍的dataview插件为obsidian提供了一定的数据检索和展示功能，属于实用的高阶插件，入门门槛很高，如果是轻度用户可以不使用本插件。该插件具体运行得到的效果就如同群友Vast & Hazy所展示的那样（上图），很吸引人。但该插件目前在发布页面，不能呈现本地的效果。

这个插件和之前介绍的timelines有2个类似的地方：
1. 需要检索yaml中的元数据信息
2. 运行时使用代码块



# 插件介绍
dataview插件是由blacksmithgu编写，此时版本是0.1.10。
Github页面： https://github.com/blacksmithgu/obsidian-dataview
蓝奏云页面： https://wws.lanzous.com/iFdUIn5rmre
官方说明： https://github.com/blacksmithgu/obsidian-dataview
本文主要参考官方说明文档，但没有全部翻译且可能翻译有误，如果大家感兴趣请直接前往说明文档页面阅读全文。

## dataview语句
dataview语句如下
````
```dataview
[list|table|task] field1, (field2 + field3) as myfield, ..., fieldN
from #tag or "folder"
where field [>|>=|<|<=|=|&|'|'] [field2|literal value] (and field2 ...) (or field3...)
sort field [ascending|descending|asc|desc] (ascending is implied if not provided)
```
````

## 语句的解释
上述语句太过复杂，我只简单介绍一些内容。

dataview有三种表现形式list、table、task。
- list：将检索到的所有内容以列表形式展现。
- table：将检索到的所有内容以表格形式展现。
- task：检索内容中所有TODO和DONE的任务，分别展示。

- Where：可以指定从某个标签（在yaml字段中的标签），或某个文件夹中检索信息。
- sort：排序：可以按某个字段进行排序，可以升序（使用参数ascending、asc）或降序（使用参数descending、desc）


Field 字段
- file.name: The file title. 文件标题
- file.path: The full file path. 文件路径
- file.size: The size (in bytes) of the file. 文件大小
- file.ctime: The date that the file was created. 文件的创建时间
- file.mtime: The date that the file was last modified. 文件的修改时间
- file.day：The date contained in the file title. 特指一类文件名具有yyyy-mm-dd（年-月-日，例如2021-03-21）特征的文件。

## yaml的设置
dataview检索的是文档的中自建的yaml字段。官方说明中games的例子，应该是在文件的yaml中附上了time-played, length, rating三个值。本文开始群友Vast & Hazy图中的Start Date、End Date和Status字段也应该是在卡片yaml中设定的，并以table形式展示。

下面的的操作就是在卡片中加上了Date字段，字段没有特殊要求，但是需要注意符合要全英文。

```
---
tags: [timeline, 美图,花]
Date: 2021-03-15
---
```

# 实际操作
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210321143545.png)
实际操作如上。大家可以前往ob教程下载， https://gitee.com/cyddgi/obsidian-chinese-help 。我这里也提供这次使用的三张卡片

## 卡片
以下三张是我制作用于演示的卡片。大家可以在ob中创建3个新的文件，将下面内容复制过去。

```
---
tags: [timeline, 美图,花]
Date: 2021-03-15
---

<span class='ob-timelines' data-date='2021-03-14-00' data-title='花朵' data-img = 'https://gitee.com/cyddgi/picture-store/raw/master/img/20210314193052.png' data-class = "customCardCSS">插入描述的区域</span> 
本图来自：https://www.pexels.com/zh-cn/photo/5706559/
```

```
---
tags:  [timeline, 美图]
Rating: 5
Date: 2021-03-14T19:32:20
---

<span class='ob-timelines' data-date='2021-03-10-08' data-title='相框' data-img = 'https://gitee.com/cyddgi/picture-store/raw/master/img/20210314193230.png' data-class = "customCardCSS"> 本图来自：https://www.pexels.com/zh-cn/photo/5797991/ </span> 

正文开始~~~
- [ ] 下载这张图片
```

```
---
tags: [timeline, 美图]
Rating: 4
Date: 2021-03-13
---

<span class='ob-timelines' data-date='2021-03-10-13' data-title='树叶' data-img = 'https://gitee.com/cyddgi/picture-store/raw/master/img/20210314193609.png' data-class = "customCardCSS"> 本图来自：https://www.pexels.com/zh-cn/photo/6805871/</span> 
正文开始~~~


- [x] 下载这张图片
```

## 展示
下面是用于展示的语句，大家在复制完上述卡片后，可以新建一张卡片，复制下面内容后，切换到预览模式。

### 以table方式来呈现
````
```dataview
table Date from #美图 
sort file.ctime desc
```
````

展示所有标签带有“美图”卡片中Yaml内的Date，并且按文件的创建时间降序。

### 以task方式来呈现

````
```dataview
task from "17 插件演示"
```
````

展示"17 插件演示"文件夹内所有的任务，包括TODO和DONE。

### 以list方式来呈现

````
```dataview
list from #美图 
sort file.size asc
```
````

以列表形式展示所有标签带有“美图”卡片，并且按文件的大小升序。

