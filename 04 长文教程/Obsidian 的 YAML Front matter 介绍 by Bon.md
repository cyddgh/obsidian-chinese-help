---
title: 
uid: 202105061533
aliases: []
tags: []
from: 
---
[[YAML（MOC）]]
本文经过[[Boninall]]授权，转载于此。原文链接： https://zhuanlan.zhihu.com/p/370113792 。
# 前言

YAML 作为一种用来写文件配置的语言，简洁而又强大，不过在 Obsidian 或者其它 Markdown 中用到的 YAML 语言知识只是一些基础，因此在此仅对 Obsidian 支持的 YAML 语法进行介绍。 在 Obsidian 中需要加上 YAML 时，需要在文件的开头（是必须在文件的开头加入）输入两个三横杠`-`，如下：

```YAML
---
YAML 语言
---
```

接着再在下边的三横杠的下边加上一个空行，以防 Makrdown 渲染器错将下一行的内容进行渲染。而这两个三横杠包括的区域一般被称为 `Front-matter` 。

如果你从之前就很在意 Obsidain 中的笔记以及文章的元数据建立，例如，你每次一定要附上创建日期以及标签以及相应的类别等，那么在笔记中插入元数据的方式，除了方便你现在检索，也方便未来的插件操作等。

不过其实在某些插件出来之前，`Front-matter` 在 Obsidian 中对于普通的笔记用户用处不大，我上一次用它的原因是因为想要写 Hexo 博客，为了快速生成网页的标题、链接等使用的。但是 Obsidian 在 0.8.0 后的版本开始大规模地改进了 `Front-matter` 的易用性以及功能性，现在它已经可以被称作不得不知的 Obsidian 知识（你可以不用，但是至少要懂）。

# 基础用法

Obsidian 其实在帮助文档中已经说得很清楚了，这里为了省力气，我直接将原文拷贝过来，

示例：

```YAML
---
key: value
key2: value2
multiple: [one, two, three]
multiple:
- one
- two
- three
---
```
你的所有参数都应当放在同一个 Front matter 中，如果是一个 field 对应多个参数的话，就需要用 `[]` 将它们概括起来，或者用 `- ` 来将它们从上到下排列 。

而在 Obsidian 0.9.16 后， Obsidian 支持的别名（alias）需要且仅能使用 `Front-matter` 中进行标注来实现。如下：

```YAML
---
alias: 别名1
aliases: [别名2, 别名3, 别名4]
aliases:
- 别名2
- 别名3
- 别名4
---
```

且 Obsidian 也支持在 YAML front matter 中插入标签（tag）的元数据，例如：

```YAML
---
tag: 标签1
tags: [标签1, 标签2, 标签3] #还可以是"#pkm"等
tags:
- 标签1
- 标签2
- 标签3
---
```

除了标签、别名外，Obsidian 没有其它的元数据原生支持，但是所有的元数据都已经存在 Obsidian 的笔记对应的 Cache 里面，因此 Obsidian 的开发者也可以根据这些 Cache 开发一些独特的插件。

# 高级用法？

Obsidian 目前使用或优化 YAML Front matter 的插件并不算多，据我所知仅有以下的几个：

- Dataview —— 根据 YAML Front matter 来生成表格
- Query2table —— 根据 YAML Front matter 来生成表格，且支持筛选，但稳定性不足
- Metatable —— 优化 YAML Front matter 的显示效果
- Text{{expand}} —— 抽取 YAML Front matter 的值
- Juggl —— 根据 YAML Front matter 的内容生成线段联系

其中 Dataview 插件以及 Query2table 插件都是“基本”基于 YAML Front matter 的数据来生成表格或者列表的，但是此处有些许的不同，Query2table 生成的表格可以让你筛选内容，以及在操作易用性上，Query2table 也许更容易学习，但是相反地，dataview 的检索功能强大而且支持多种检索排序等，两者生成的表格分别支持了不同的特性，其中 Dataview 已经支持 CSS 定义对应的样式，而 Query2table 的上一次更新已经是四个月前的事情了。

如果你已经按部就班设置了适合自己的 YAML Frontmatter ，那么你可以根据以下的代码块适应性修改来生成自己的 Dataview 表格：

```
​```Dataview
table Completed, Priority, Project, defer-date as "Defer Date", due-date as "Due Date", recur-length as "Recur Length", defer-date + recur-length as "Next Date"
from #tasks
where defer-date < date(now) and completed != 1
sort doDate asc
​```
```

其中 table 后边跟着的是每一列的列名称（对应 YAML Front matter 的参数），这些列的名称可以自定义也可以用原来的 YAML Front matter 的名称，from 指的是基于标签、文件关键词或什么检索式等（默认支持标签），where 指的是上边我们获取的所有笔记中匹配对应的要求的，例如这里的意思就是“目前还没完成的任务或笔记”，sort 指的是要怎么排序；由于 Dataview 有很多的不同的参数供你来获取从而生成对应的表格，因此此处请务必参考官方的文档：[Dataview Document](https://blacksmithgu.github.io/obsidian-dataview/#/)；此外，关于 Dataview 的文章也在来的路上了 #FLAG 1。

如图1为 Dataview 生成的表格：

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210506153500.png)



---

而 Query2table 也是类似的，采用下方的代码生成：

```
​```query2table
query: "tag: article"
fields: 
	- title: note
	- status: text
approxNumberOfResults: 5
​```
```

其中 query 指的是采用什么检索式，这里的检索式采用 Obsidian 支持的检索式即可，fields 指的是将哪些 YAML Front matter 的参数拿来使用，最后approxNumberOfResults 指的是获取多少行。

如图2为 Query2table 生成的表格：

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20210506153528.png)



至于 Text{{expand}} 中关于 YAML Front matter 的用法则请查看我之前的文章： [Obsidian 插件之 Text{{expand}} ](https://zhuanlan.zhihu.com/p/369655284)

而 Juggl 插件这里暂且不表，后续会专门写一篇关于 Juggl 的文章，到时候会介绍对应的使用方式。 #FLAG 2

# 我的设置

因为我在使用 Obsidian 的时候更多是考虑笔记是否要写成文章，或者笔记与原文的关系，所以我的 YAML Front matter 一般会有以下的参数：

```
title: 实际文件名，因为我的文件名可能会是数字串
date: 建立日期
tags:
  - 标签1
alias: 别名1
category: 类别
stars: 星级（可选，当为评测笔记的时候会存在）
from: 基于什么，来自什么
url: 文章链接（如果已经发文或者已经存在在 Obsidian publish 上的话）
```

上述的几个参数是我日常中最常用的参数，有些情况下，会加上本地的双链，用 `bi-links:` 来概括，通过这些参数，我经常的一个应用就是查看自己过去一段时间内的所有文章或者笔记列表，而且查看其中可以用来分享的，但是还没写成文章的，以及各个 FLAG。


# 总结

以上就是 Obsidian 的 YAML Front matter 的简单介绍，用 Obsidian 对笔记进行元数据管理的时候，采用 Front matter 的方式管理，然后使用插件快速获取对应的元数据或者展示对应的元数据，显然可以让自己的笔记不再局限于单篇笔记的内容，而是利用联系展示多篇笔记之间的关系，如果你熟练地使用 YAML 进行元数据的管理的话，将来即使迁移到别的软件中，也可以轻易地利用脚本将对应的元数据转化成对应的笔记软件所支持的元数据形式。

