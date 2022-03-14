---
uid: 20220226081914
aliases: []
---
# 引言
Table of Contents，我个人翻译为目录。在办公软件word中可以通过设置大纲级别，然后自动插入目录，进行相关的跳转。在obsidian中，Dynamic Table of Contents（Dynamic TOC）插件可以依据不同等级的标题（例如`#`，`##`），自动生成目录。

# 插件名片
Dynamic Table of Contents插件是由Aidurber开发，目前版本是0.0.26。

Github地址： https://github.com/Aidurber/obsidian-plugin-dynamic-toc

# 实际操作
## 插件设置
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220226082612.png)

- List style：设置目录的实现形式，有3种bullet、number | 和inline。
- Minimum Header Depth：最小目录深度，默认是2（对应`##`），建议设置为1（对应`#`）。
- Maximum Header Depth：最大目录深度，默认是6（对应`######`）。

## 插入代码
在ob中插入以下代码，该插件就能生效
````
```toc

```
````

例如ob中有以下文本

```
# 知识管理
## 知识管理工具
### obsidian

### RoamResearch

## 知识管理信息源

# 时间管理

# 财富管理
```

生成的目录如下

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20220226083433.png)

如果你需要更多的样式设置，或者进行单一的设置，可以参考官方文本，在代码块中输入更多的参数。

````
```toc
	style: bullet | number | inline (default: bullet)
	min_depth: number (default: 2)
	max_depth: number (default: 6)
	title: string (default: undefined)
	allow_inconsistent_headings: boolean (default: false)
	delimiter: string (default: |)
	varied_style: boolean (default: false)
```
````