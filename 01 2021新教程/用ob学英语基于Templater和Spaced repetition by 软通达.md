---
uid: 20220413150323
aliases: []
---
# 引言
本工作流主要基于[[Templater（模板增强插件）]]和[[Spaced repetition（间隔复习插件）]]。其在算法上可能不是很先进，但方便之处在于可以快速制卡，全程在obsdiain中完成，操作简单。发音是依靠有道的在线发音，减少了库的大小。

# 实际操作
## Templater模板构建
需要先设置一个Templater的模板，设置的模板名称为“FlashCard复习模板”（你可以自选名称），并放置在库目录中的Template文件夹中，内容如下：

```
---
uid: <% tp.date.now("YYYYMMDDHHmmss") %>
aliases: []
---
#flashcards 

<% tp.file.title %>
<audio  
src="http://dict.youdao.com/dictvoice?audio=<% tp.file.title %>" controls="controls"> 
</audio> 
?
<% tp.file.cursor() %>
```

## 在库中应用Templater模板
在Templater插件中Folder Templates中设置新的Folder template，让新建卡片都自动套用这模板，即生效目录设为`/`。

## 阅读步骤简述
然后导入一段你要学习的英语文本，对不懂的词语进行打上双链，然后点击双链，就会自动创建一个新卡片。以单词“algorithm”为例，我创建的卡片如下：

```
---
uid: 20220413142051
aliases: []
---
#flashcards 

algorithm
<audio  
src="http://dict.youdao.com/dictvoice?audio=algorithm" controls="controls"> 
</audio> 
?
算法
```

“算法”，两个字是我自己打的。

# 待改进的点
我目前思考有以下几个方面，如果有高手可以解决，请留言：
- 如何用Templater来获取音标
- 关于发音有没有更好的方法，更方便好用的音源
- 能不能内嵌视频进行学习，例如[[基于ELL扩展获得YouTube双语字幕时间戳并在Obsidian中复用 by 彭文波]]所演示的那样。