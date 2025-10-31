---
uid: 20221124181047
aliases: []
---
作者: [[LincZero]]
论坛地址： https://forum-zh.obsidian.md/t/topic/12670

# Md实用标签

# 目录

# Md实用标签

==【注意】==

- 写作时优先使用Md自带的语法，**少用**HTML标签。几个原因：

  1. 实在想要极度样式丰富，那为什么不直接使用富文本编辑呢

  2. 应当重视实际内容与效率

     Markdown语法简单就是为了把更多精力放在 “写” 上，不要本末倒置，花 “大精力” 去修饰文章

     除非在有 “工具栏” 的情况下，不影响写作效率时，可以适当使用（例如Ob 思源等有工具栏插件、掘金等一些博客也会自带工具栏）

  3. 语法简单与样式简单

     过多地使用样式，反而容易找不到重点。一篇文章应该使用较少的几种样式，减少地去圈重点（处处重点等于没重点）

- 当然，在一些情况下，使用HTML标签去丰富样式是有利的。比如：

  - 想要丰富的格式，但某些平台只能使用Markdwon写作时
  - 产品级文档（不是指技术文档，那种也没必要，除非你有专门的部门去干。主要是单页的主要文档）
    - 比如某个项目的介绍文档，比如简历等（但这些一般都用富文本格式吧）
    - 这时可以**减少对效率的极致需求**，花多一些精力去对文档进行润色，是合适的
  - 某些专题的笔记
    - 比如在写注音笔记、或翻译来的文档时，ruby + rt 标签会很有用，可以保留原单词的同时又可以不让这些单词影响阅读体验
    - 比如在软件介绍时，使用 kbd 标签（最好加个样式），看起来更直观

- 总之，合理使用就好



## 可使用

### 标签类

| 标签 | 作用          | 使用建议                 |
| ---- | ------------- | ------------------------ |
| br   | 换行<br/>换行 | 比如表格内换行就使用上了 |



### Sytle类

| Sytle内容                  | 作用                                                         | 使用建议                                                     |
| -------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 图片高宽控制<br />或者缩放 | <img src="https://img0.baidu.com/it/u=3452693033,2914629743&fm=253" style="height:100px"><img src="https://img1.baidu.com/it/u=692181697,2515657060&fm=253&app=120&size=w931&n=0&f=JPEG&fmt=auto?sec=1665680400&t=73a9efc9b1274679e2ee4c6a155a98ea" style="height:100px"> | 我主要是在表格内使用。让他们的高或宽相同（固定px）<br /><br />完美解决对齐问题（图片本来一大一小）<br />图片缩放也行，比如50%，但一般我会给固定大小而非百分比 |
| 右浮动                     | <p style="float:right">左</p><br /><p align="right">左</p>   | 用得不多                                                     |




### 特殊情况使用

一般是专题笔记才用，如没必要勿使用

| 标签      | 作用                                                         | 使用建议                                                     |
| --------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ruby + rt | <ruby>国家<rt>Nation</rt></ruby> | 技术翻译文档里比较常见的（Typora复制有bug）<br />（这个最好字体在18px以上效果较好） |
| kbd       | <kbd>Ctrl</kbd> + <kbd>C</kbd><br /><kbd>Ctrl Shift</kbd> + <kbd>V</kbd> | 主要是快捷键用<br />觉得原生的样式有点一般的，也可以调整一下css |
| u         | <u>下滑线</u>                                                |                                                              |
| center    | `<center>居中</center><br />`（正文生效）                     | 非必要，勿使用                                               |
| abbr      | <abbr title="kubernetes">k8s</abbr>                          | 缩写，可以为一些缩写添加注释                                 |

> [!warning]
> 现已不再推荐 `center` `font` `big` 等标签，不利于结构与样式分离，且他们在HTML4中已经被废弃，并在某些环境中可能报错
> 
> ```bash
> [Vue warn]: Failed to resolve component: center
> 665If this is a native custom element, make sure to exclude it from component resolution via compileroptions.isCustomElement.
> 666[Vue warn]: Failed to resolve component: font
> 667If this is a native custom element, make sure to exclude it from component resolution via compilerOptions.isCustomElement.
> ```

兼容性
（以下表头缩写分别为：Obsidian、Typora、CSDN、掘金、Github、用于代替的HTML标签。）

| 扩展语法  | Ob   | Ty   | CS   | 掘   | Gi   |
| --------- | ---- | ---- | ---- | ---- | ---- |
| ruby + rt | 🟩    | 🟩    | 🟩    | 🟩    | 🟩    |
| kbd       | 🟩    | 🟩    | 🟩    | 🟥    | 🟩    |
| u         | 🟩    | 🟩    | 🟩    | 🟥    | 🟥    |
| center    | 🟩    | 🟩    | 🟩    | 🟥    | 🟥    |
| abbr      | 🟩    | 🟩    | 🟩    | 🟩    | 🟥    |



### 用标签代替扩展语法

有对应的扩展语法，就说明有相关的使用需求。
与html标签相比，扩展语法的优点是写得快，缺点是不如html标签兼容性好。

| 扩展语法                   | HTML<br />代替标签                                           | 效果                  |
| -------------------------- | ------------------------------------------------------------ | --------------------- |
| [[双链]]                   | ——                                                           | ——                    |
| $内联公式$ (\$\$)          | ~~个别符号：特殊方式打出、`&`转义、unicdoe强行输出。~~<br />~~上下标的表示也有。但像分母、矩阵等，没办法。~~<br />这个没必要转HTML标签的，还是能直接用的 | ——                    |
| ==高亮== (\=\=)            | mark                                                         | <mark>mark高亮</mark> |
| 上标^2^ (\^\^)             | sup                                                          | 上标<sup>2</sup>      |
| 下标~2~ (\~\~)             | sub                                                          | 下标<sub>2</sub>      |
| %%ob注释%% (\%\%)          | html注释                                                     | <!--注释-->           |
| ob table extended 插件表格 | table（不要手动写，有在线转化工具，随便搜一下就有）          | 略                    |



兼容性：
（以下表头缩写分别为：Obsidian、Typora、CSDN、掘金、Github、用于代替的HTML标签。）
（第一个方块表示对扩展语法的兼容性，第二个方块表示替换成HTML标签后的兼容性，没有或黑色方块表示就没有没有该扩展语法的替换方案）

| 扩展语法          | Ob   | Ty   | CS   | 掘   | Gi   |
| ----------------- | ---- | ---- | ---- | ---- | ---- |
| 双链              | 🟩    | 🟥    | 🟥    | 🟥    | 🟥    |
| 内联公式          | 🟩    | 🟩    | 🟩    | 🟩    | 🟥    |
| 高亮              | 🟩🟩   | 🟩🟩   | 🟩🟩   | 🟥🟩   | 🟥🟥   |
| Ty上下标          | 🟥🟩   | 🟩🟩   | 🟥🟩   | 🟥🟩   | 🟥🟩   |
| ob 注释           | 🟩🟩   | 🟥🟩   | 🟥🟩   | 🟥🟩   | 🟥🟩   |
| ob table extended | 🟩🟩   | 🟥🟩   | 🟥🟩   | 🟥🟩   | 🟥🟩   |



总结：

内联公式和高亮虽然属于md的扩展语法，但兼容性较好，而且就算不支持也不会有什么严重后果，可以放心使用。
其他扩展语法均建议优先使用html标签作为替换方案。
像双链这种即是扩展语法，又没替换方案的，就没办法了



## 不建议使用

### 一般不建议

| 标签                                        | 作用                                                         | 使用建议                                                     |
| ------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| font + style样式<br />主要是face size color | `<font style="color:red">红色</font><br /><font style="color:blue">蓝色</font><br /><font style="color:green">绿色</font><br /><font style="color:cyan">青色</font>` | 看到有的人比较喜欢使用这个。<br />其实还是可以用，如果有工具栏，并且能保证不会以纯文本方式编辑。<br />反正我不喜欢 |
| class                                       | <p class="custom">自定义</p>                                 | 自定义了一个class，来使用自定义样式                          |

> [!warning]
> 现已不再推荐 `center` `font` `big` 等标签，不利于结构与样式分离，且他们在HTML4中已经被废弃，并在某些环境中可能报错
> 
> ```bash
> [Vue warn]: Failed to resolve component: center
> 665If this is a native custom element, make sure to exclude it from component resolution via compileroptions.isCustomElement.
> 666[Vue warn]: Failed to resolve component: font
> 667If this is a native custom element, make sure to exclude it from component resolution via compilerOptions.isCustomElement.
> ```

### 没有任何用的必要

一般**不使用**这些标签，因为 md 自身有更简单的写法

| 标签            | 作用                           | 代替                                                |
| --------------- | ------------------------------ | --------------------------------------------------- |
| b               | <b>强调</b>                    | **用md自身语法代替**                                |
| i<br />em       | <i>斜体</i><br /><em>强调</em> | *用md自身语法代替*<br />（有区别的，md斜体用的是em) |
| del             | <del>删除</del>                | ~~用md自身语法代替~~                                |
| h1 (表格外有效) | <h1>1级标题</h1>               | # 1级标题                                           |
| h2 (表格外有效) | <h2>2级标题2</h2>              | ## 2级标题                                          |
| h3 (表格外有效) | <h3>3级标题1</h3>              | ### 3级标题                                         |
| ……              | ……                             | ……                                                  |



### 纯炫技，毫无卵用


> #### details

隐藏内容，点击展开。兼容性还可以，就算不支持也只是展开而已


| 标签    | Ob   | Ty   | CS   | 掘   | Gi   |
| ------- | ---- | ---- | ---- | ---- | ---- |
| details | 🟩    | 🟩    | 🟥    | 🟩    | 🟩    |

效果：

<details>
  <p>我是一段被隐藏的内容</p>
</details>



> #### progress

显示进度条，而且兼容性很差。


| 标签     | Ob   | Ty   | CS   | 掘   | Gi   |
| -------- | ---- | ---- | ---- | ---- | ---- |
| progress | 🟩    | 🟥    | 🟥    | 🟥    | 🟥    |

效果：

<progress max="100" value="60"/>

这个兼容性已经很差了，后面的那几个基本上兼容性都不会好。后面的我就不一一地去试兼容性了



> #### figure

可以给图片一个文字说明。效果：

<figure>
    <img src="https://img2.baidu.com/it/u=2231228778,2513904551&fm=253" height="120">
    <figcaption>这是一张大象的照片</figcaption>
</figure>




> #### area

为图片提供点击热区，可以自己规定一张图的哪些区域可点击；一般配合map使用。效果：

<div>
	 <img src="https://img1.baidu.com/it/u=692181697,2515657060&fm=253&app=120&size=w931&n=0&f=JPEG&fmt=auto?sec=1665680400&t=73a9efc9b1274679e2ee4c6a155a98ea" width="100" height="100" alt="" usemap="#map">   
    <map name="map">                    
        <area  shape="rect"coords="0,0,100,50"alt="baidu"href="https://www.baidu.com">       
        <area shape="rect" coords="0,50,100,100" alt="sougou" href="https://www.sogou.com/">   
    </map>
</div>






