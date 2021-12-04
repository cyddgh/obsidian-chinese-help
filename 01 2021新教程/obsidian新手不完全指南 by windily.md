---
title: 
uid: 202111122205
aliases: []
tags: []
from: 
---
https://forum-zh.obsidian.md/t/topic/1628

适用于所有人
======

ob 是什么
------

> Obsidian is a powerful **knowledge base** on top of a **local folder** of plain text Markdown files.

这是 ob 官网对 ob 的核心介绍。翻译过来就是：“obsidian 是构建在一个本地文件夹中的知识库，文件夹中放的是一些纯文本 Markdown 文件。”

针对这句话有几点需要阐明的是：

1.  ob 是知识库管理工具，不单单是文字编辑器，和 word，vim，notepad++ 这些有本质上的区别。学习 ob 的目的不仅仅是为了记笔记，而更多的是打造自己的知识体系，ob 提供笔记管理的工具罢了。这些工具包括但不限于：优化输入体验（vim 模式，模板，自动补全，代码高亮，智能列表，折叠缩进，智能粘贴，图片、音频、视频、网页等多媒体插入），笔记关联（双链，标签，块引用，关系图谱），高度开放的插件系统（目前计算机技术能实现的东西基本上都能在 ob 里实现，只是适不适合和值不值得的问题）。基于此，把 ob 理解为一款编辑器是很初级的看法。
2.  ob 是本地的软件。顾名思义，ob 不依赖于网络就可以正常运行，所有的数据都保存到本地，数据永远在自己手里。
3.  ob 知识库就是一个文件夹。ob 管理的所有数据都存在于一个文件夹中，这个文件夹称之为库 (vault)，包括配置文件和笔记文件。其中配置文件以`.obsidian`存在于库的根目录中，管理着 ob 的主题，样式，插件和一些运行时的数据。
4.  ob 构建于 Markdown 文件之上。Markdown 文件是以`.md`结尾的文件，内部是纯文本，可以用任何编辑器打开。md 文件不仅仅有笔记的记录，还有格式的记录。

Markdown 是什么
------------

首先要明白的是一篇可读性好的笔记可以粗浅的分为内容和格式两个部分，在计算机中可以用标记语言来同时描述内容和格式，主流的是 HTML/XHTML，是由一对尖括号进行标记，如下所示，其中：

*   `<font>`被称为标签，描述内容的类型，以便赋予内容默认的格式，除此之外还有`<h>`、`<p>`、`<audio>`等，分别代表标题，段落，音频
*   `color="red"`描述的是样式，即文字的格式是什么样的，通常可以独立成一个后缀为`.css`的文件
*   被`><`夹住的部分就是内容

```
<font color="red">红色内容</font>


```

但书写这样的内容显然可读性不好，且比较麻烦。一般普及到大众有两种方式：

1.  鼠标操作：类似于 word 这样的，其底层依旧是 HTML/XHTML 或 XML 这样的标记语言，不信的话你把 docx 后缀的文件直接解压看看有什么。不同之处是利用鼠标或快捷键直接对选中的默认样式添加样式标签，再在界面上显示出来。这样的话，人们只看得到格式的变化，而看不到标签。
2.  键盘操作：类似于 Markdown 这样，将格式标记精简成`# ## ==` 这样，有利于键盘快速操作，但同时牺牲了格式调整，可喜的是可以和 HTML 混编。

下面正式介绍 Markdown：  
Markdown 是一种轻量级标记语言，排版语法简洁，让人们更多地关注内容本身而非排版。它使用易读易写的纯文本格式编写文档，可与 HTML 混编，可导出 HTML、PDF 以及本身的 .md 格式的文件。因简洁、高效、易读、易写，Markdown 被大量使用，如 Github、Wikipedia 等网站，如各大博客平台：WordPress、Drupal、简书等。  
千万不要被「标记」、「语言」吓到，Markdown 的语法十分简单，常用的标记符号不超过十个，用于日常写作记录绰绰有余，不到半小时就能完全掌握。就是这十个不到的标记符号，却能让人**优雅地沉浸式记录，专注内容而不是纠结排版**， 达到「心中无尘，码字入神」的境界。

学习方法与学习资源：

*   学习方法：学习自行车看一遍别人怎么骑的，自己马上实践，便是最好的方式，别去研究自行车为什么不会倒，甚至还顺便做点笔记 -.-。能直接上手用就别去研究，Markdown 同理。
*   学习资源：ob 的帮助库，打开 ob 的左下角倒数第二个按钮。

下面是我的一些见解，可看可不看，但我必须说：

> 首先 ob 的定位是知识库管理工具，不是类似于 word 这样做海报，做宣传手册。知识库中的笔记一定要有一致性，以方便检索和查看，对什么内容在什么地方应一目了然，格式一旦确定便不应更改。Markdown 具有这个性质，便被用上了，这是非常自然和合理的。但依旧会有人吐槽 Markdown 的设计哲学：
> 
> > 问：Markdown 不能表格合并，表格也极其反人类，不好用  
> > 答：Markdown 能通过 HTML 合并表格。Markdown 本就是 HTML 简化的产物，对于简化得不优雅的东西当然就舍弃。如果你嫌用 HTML 太麻烦。那你何不通过 ob 设计一种新的格式语言，使用 codeblock 能很好的实现。这本是简洁与繁杂的权衡，每个人取舍不一样。不服的话要么自己写，要么白嫖他人的。如果连他人都没有实现，那肯定是你自己的问题。  
> > 问：ob 为什么不做成 word 那样的编辑器，给个可选项也好呀！  
> > 答：键盘效率输入远比鼠标输入效率高，收获远比付出得多。被 word 养出来的思维惯性是可以改变的，为了适配这种惯性我认为是不值得的。会技术的人认为 markdown 效率高，没必要去做相关适配。不会技术的人不认为效率高，也做不了适配。  
> > 问：Markdown 好难学，劝退劝退劝退  
> > 答：那你不应该做知识管理，这个更难。

使用 ob 你必须了解的
------------

### 关于 ob

[About - Obsidian](https://obsidian.md/about)  
[关于 obsidian 为什么不开源的解答](https://forum.obsidian.md/t/open-sourcing-of-obsidian/1515/38)

> 为什么要开发另一个笔记应用程序呢？  
> 就像那些陈词滥调一样，我们创办 obsidian 公司是因为 Erica 找不到任何东西能满足她建立个人知识库的需要。她已经尝试了从 TiddlyWiki 到大脑的各种软件，但是没有一种感觉是正确的。  
> 疫情隔离终于给了我们开始制作的机会。经过更多的思考，我们决定了 obsidian 的三个最基本的方向:
> 
> *   **Local-first and plain text 本地优先和纯文本**;
> *   **Link as first-class citizen 链接作为第一类公民**;
> *   **Make it super extensible. 使它具有超强的扩展性**
> 
> 虽然我们称之为个人知识库或者你的 “第二大脑”，但是我们也喜欢把它看作是你笔记的 IDE。你可以把 IDE 想象成一个强大的前端，它试图理解你的代码，比如函数和变量存储在哪里，它们的类型是什么，这样做可以使你在输入代码时非常容易地浏览代码和获取建议。
> 
> 从这个意义上说，对于目前大多数的笔记应用程序来说，使用笔记就像是在编写代码时没有语法突显、代码自动完成或者与 Git 集成。所有程序员几十年来认为理所当然的事情。你不觉得这很悲哀吗？今天的知识工作者一直面临着新的挑战，他们应该得到更好的工具。
> 
> 是的，这就是为什么我们正在开发 “又一个笔记应用程序”。
> 
> 在 obsidian 之前，我们从 2015 年就开始研究 Dynalist，在此之前我们一起做过 10 多个副项目

目前的开发者有四位，分别是：

*   Shida Li：负责后端，之前在 Dropbox 和 Linkin 工作，滑铁卢大学 17‘ 软件工程专业
*   Erica Xu：负责前端和 UI，之前在 Quizlet 工作，滑铁卢大学 16’计算机科学专业
*   Sandy：办公室一号喵，轻音体柔喵喵叫。
*   Blaze：办公室二号喵，像狗一样贼有活力，爱玩捉迷藏，更爱摇尾巴。

正是这两位大佬和数百位插件开发者创造了 obsidian 如此繁荣的生态，提供给个人**完全免费**的知识库管理工具。所以在碰到某些问题时多想想，我们是共同创造一项推动人类发展的事业。有技术的写插件，fork 项目修 bug，加 feature，没技术的反馈 bug，提 issue，每个人都有能力也有机会使得 obsidian 更好。——_致那些只会白嫖且爱 BB 的人_

### 学习路线

(仅代表我的个人建议)

ob 既然是知识库管理软件，那必须了解的一定是基础操作：

*   官方示例库
*   [Ob 软件基础操作教程 - 蚕子 8](https://www.bilibili.com/video/BV1qD4y1m7nv)：非常详细的视频介绍
*   [落山鸡编辑与维护的中文文档 3](https://publish.obsidian.md/chinesehelp)：内容多而全，是我的启蒙文档，可以探索到很多东西

其次是关于 ob 的最新情况及相关讨论：

*   QQ 群：774176839
*   [discord 官方讨论群 1](https://discord.com/invite/veuWUTm)
*   [obsidian 最新消息推送 - 英文](https://www.obsidianroundup.org/)
*   [obsidian 开发计划 1](https://trello.com/b/Psqfqp7I/obsidian-roadmap)
*   [obsidian 中文论坛 2](https://forum-zh.obsidian.md/)
*   [obsidian 英文论坛](https://forum.obsidian.md/)

大致了解了 ob，做了一定量的笔记，在提问之前建议先阅读：

*   [《提问的智慧》精读注解版 (rymcu.com) 3](https://rymcu.com/article/80)

之后最重要的是自己笔记系统的建立，可以通过学习模仿别人的笔记思路，找到适合自己的笔记方法。如果可以的话，有自己的体系后我建议分享出来，让大伙儿帮你看看有哪些可以优化的同时，帮助其它的人：

*   [如何构建笔记系统 - 实际操作篇 - Ryooo 3](https://zhuanlan.zhihu.com/p/353521308)
*   [如何构建自己的笔记系统？ - 知乎 (zhihu.com) 2](https://www.zhihu.com/question/23427617)
*   [Latest Knowledge management topics - Obsidian Forum](https://forum.obsidian.md/c/knowledge-management/6)

这部分内容中文论坛由于创建的较晚，并没有相关内容。建议去找找文献，问问大佬。

接着便是入插件坑，插件基本上都是世界各地开发者无偿开源制作的，在 Github 托管。此处可以找到关于插件最新消息，里面记录了插件的详细使用方式和使用文档，同时可以反馈给作者 bug 或者需求，作者都很 nice。为了方便新手了解插件，推荐下载量前几名的插件：

1.  [liamcain/obsidian-calendar-plugin](https://github.com/liamcain/obsidian-calendar-plugin)：给 ob 加上日历视图，可以跳转到每日笔记
2.  [tgrosinger/advanced-tables-obsidian](https://github.com/tgrosinger/advanced-tables-obsidian)：markdown 表格增强工具，能更快速的制作表格
3.  [blacksmithgu/obsidian-dataview](https://github.com/blacksmithgu/obsidian-dataview)：高性能笔记查询引擎，提供 JavaScript API
4.  [deathau/sliding-panes-obsidian 1](https://github.com/deathau/sliding-panes-obsidian)：让编辑器变成滑动窗口，试了才知道妙处
5.  [mgmeyers/obsidian-kanban](https://github.com/mgmeyers/obsidian-kanban)：基于 Markdown 创建看板视图
6.  [SilentVoid13/Templater](https://github.com/SilentVoid13/Templater)：模板引擎，能插入变量和函数
7.  [vslinko/obsidian-outliner](https://github.com/vslinko/obsidian-outliner)：无序列表增强，快捷操作无序列表
8.  [lynchjames/obsidian-mind-map 2](https://github.com/lynchjames/obsidian-mind-map)：思维导图

目前插件数量已破 300 款，需要自己去探索符合你工作流的，如果需要推荐，可参考插件试用大佬的笔记：

*   [obsidian 软件技巧 - 知乎 (zhihu.com)](https://www.zhihu.com/column/c_1302994040707948544)
*   [历经一年，我保留了这些 Obsidian 插件 - 知乎 (zhihu.com) 2](https://zhuanlan.zhihu.com/p/410202700)

以及 github 资源：[kmaasrud/awesome-obsidian: ![](https://forum-zh.obsidian.md/images/emoji/twitter/dark_sunglasses.png?v=10) Awesome stuff for Obsidian (github.com)](https://github.com/kmaasrud/awesome-obsidian)

最后是活跃在互联网上的分享者，这些资源可以通过搜索引擎找到，包括但不限于知识管理，ob 插件使用，多软件联动，如：

*   [八角经刀的视频 - bilibili 1](https://space.bilibili.com/241033241)
*   [dataview 插件的使用 - 理行天道](https://www.jianshu.com/u/56a8cbef0e7a)

如何修改 ob 的默认样式
-------------

1.  使用主题
2.  使用带样式调整的主题，通过 style settings 插件调整，如：blue topaz，ITS，minimal 等
3.  寻求社区，Q 群分享的样式片段，控制 html 样式的是以`.css`结尾的片段，放在`.obsidian/snippets`路径下，供 ob 中外观设置中调用。
4.  向主题作者反馈需要的样式，反馈方式在主题的 github 页面内，登陆后点击 issues，发表你的看法。
5.  自己写自定义样式片段 [Obsidian 主题样式修改半入门教学 - 经验分享 - Obsidian 中文论坛 1](https://forum-zh.obsidian.md/t/topic/180)

以上四步循序渐进，没有开发背景谨慎自己写自定义样式片段，性价比太低，前端远比网上说的要繁琐，因为 css 是不正交的，新手容易出很多意料之外的问题。

如何访问社区插件
--------

由于 ob 的社区插件构建在 github 上，国内访问可能存在问题，因此提供以下方式解决，根据关键字搜索教程，不详述：

*   [Steam++ 开源软件](https://steampp.net/)：修改 hosts 文件，反向代理实现
*   github 加速服务：[Releases · dotnetcore/FastGithub 1](https://github.com/dotnetcore/fastgithub/releases)
*   插件搬迁网友：[宏沉一笑 - 插件发布与更新通知 - 经验分享 - Obsidian 中文论坛 1](https://forum-zh.obsidian.md/t/topic/1182)，他还做了个插件
*   插件访问修复：[完美解决 obsidian 无法加载第三方插件（社区插件）的问题 - 经验分享 - Obsidian 中文论坛](https://forum-zh.obsidian.md/t/topic/1627)
*   科学上网

ob 同步问题
-------

[obsidian 多端同步专题 - 经验分享 - Obsidian 中文论坛 5](https://forum-zh.obsidian.md/t/topic/981)：很详细了，不赘述

适用于开发者或进阶使用
===========

ob 是什么
------

ob 是基于 electron 构建的应用程序。以 electron 构建的应用程序有：vscode，Microsoft Team，WhatsApp 等，有开源，跨平台的特征。

由于 Electron 基于 Chromium 和 Node.js 构建应用，所以可以使用 HTML, CSS 和 JavaScript 常规 web 开发特性，还可以通过 Node.js 访问本地文件及操作系统 API，这是浏览器做不到的。因此，ob 支持调用 python，go 等脚本的同时，支持利用 ob 的 api 更改 UI 和操作逻辑。

如何调用脚本
------

目前我知道的有三种方式：

1.  写插件
2.  调用插件提供的脚本接口
3.  外部脚本直接操作 md 文档：不能访问 ob API 且需要打开其他界面，失去了操作一致性。

写插件能在渲染进程和主进程中运行逻辑，调用插件提供的脚本接口只能调用暴露出来的 ob 的 API。支持此种操作的插件我目前使用的是 quickadd 和 dataview。

其中 quickadd 在 macro 类型里能调用库中指定目录下的 script，仅支持 JavaScript。但通过 node 进程中的`exec`函数，能调用其它语言类型的脚本。dataview 支持在编辑器中直接写脚本，支持的也是 JavaScript。

脚本的一些实践
-------

示例：

*   [『晒晒我的工作区』个人主页面板 - 经验分享 - Obsidian 中文论坛 4](https://forum-zh.obsidian.md/t/topic/1408)
*   [库统计脚本片段 1](https://github.com/torantine/obsidian-snippets#across-vault-word-count)
*   [用 Obsidian 追踪项目（Metaedit、Dataview 及 Kanban） - 经验分享 - Obsidian 中文论坛](https://forum-zh.obsidian.md/t/topic/374)

以下脚本可以在 quickadd 中配置成命令，配合 button 插件能实现一键打开库路径下的控制台，我常用于 git 做分支笔记，对比修改历史，推送等。

```
const child_process = require('child_process')
const openTerminalCommand = "wt -d  D:\\Temp\\14-Obsidian-demo"
module.exports = async (params) => {
  await child_process.exec(openTerminalCommand)
}


```

以下脚本在 quickadd 中配置成命令，划选关键字作为文件夹名称，同时在文件夹下创建同名笔记。

```
module.exports = async (params) => {
  //获取选区并替换成链接
  let view = params.app.workspace.activeLeaf.view
  let selection
  if (!view) {
  } else {
    let view_mode = view.getMode(); 
    switch (view_mode) {
          case "preview":
            break;
          case "source":
              if ("editor" in view) {
                  selection = view.editor.getSelection(); 
                  view.editor.replaceSelection(`[[${selection}]]`); 
              }
            break;
          default:
              break;
      }
  }
  let noteName = selection

  //构造文件路径
  basePath = params.app.vault.adapter.basePath
  currentFilePath = params.app.workspace.activeLeaf.view.file.path
  fullPath = basePath + "\\" + currentFilePath
  createNewDirPath = fullPath.substring(0, fullPath.lastIndexOf('/')) + '\\' + noteName
  


  await params.app.vault.adapter.fs.mkdirSync(createNewDirPath)
  const fileDescription = params.app.vault.adapter.fs.openSync(createNewDirPath+ '\\' + noteName + '.md', 'w')
  await params.app.vault.adapter.fs.closeSync(fileDescription)
}


```

利用 dataview 提取目的标签所在的行内容形成表格，用于整库的标签汇总：

```
const files = app.vault.getMarkdownFiles()

let arr = files.map(async(file) => {
  const content = await app.vault.cachedRead(file)
  let lines = await content.split("\n").filter(line => line.includes("#todo"))
    //console.log(lines)
  return ["[["+file.name.split(".")[0]+"]]", lines]
})

Promise.all(arr).then(values => {
    const beautify = values.map(value => {
        const temp = value[1].map(line => { return line.trim().split('#')[0].substr(2)})
        return [value[0],temp]
    })
    const exists = beautify.filter(value => value[1][0] && value[0] != "[[Dashboard]]")
    dv.table(["文件", "出处"], exists)
})


```

利用 dataview 填充模板，在笔记内显示入链和出链，这里用的是 dataview 的 Sql 语法：

```
list from [[#]] 
list from outgoing([[#]])


```

总的来说，脚本配合插件能做到你想做的任何事，管中窥豹，可见一斑。

常用资源
----

*   [obsidianmd/obsidian-sample-plugin (github.com) 2](https://github.com/obsidianmd/obsidian-sample-plugin)：插件模板
*   [obsidianmd/obsidian-api (github.com)](https://github.com/obsidianmd/obsidian-api)
*   [pjeby/hot-reload 1](https://github.com/pjeby/hot-reload)：插件热加载，类似于 vscode 中的 live serve，用于插件开发
*   [（转载）Obsidian 开发相关（简单引导） - 开发讨论 - Obsidian 中文论坛](https://forum-zh.obsidian.md/t/topic/148)
*   [quickadd 源码及文档 - github](https://github.com/chhoumann/quickadd)：包含 quickadd 提供的四个类型、数个示例、quickadd API、格式语法、inline script、macros
*   [Dataview 文档 - githubio](https://blacksmithgu.github.io/obsidian-dataview/)
