---
uid: 20230904213104
aliases: []
---
Tiddlywiki是一个历史悠久的笔记平台，至今依然有很强的生命力，许多开发者活跃在这个领域中。例如国内的开发者在近年推出的衍生版本TidGi（太记） 。

Tiddlywiki支持md语法，并且以HTML网页形式保存，只需要用到静态语言，因此能部署在一些免费的发布平台，例如Github（见 https://kookma.github.io/Tiddlywiki-and-GitHub-Pages ）。因此我很早就设想用Tiddlywiki来免费发布ob库，而今天刚好看到了tiddly-gittly的tidgi-obsidian-manager插件，解决了这个问题。下图是我用该方案做的ob中文教程发布：

![](https://gitee.com/cyddgi/picture-store/raw/master/img/202309042138464.png)

tidgi-obsidian-manager插件页面和教程： https://github.com/tiddly-gittly/tidgi-obsidian-manager

因为上述页面中的信息不是很丰富，我简单介绍一些操作。

# 实际操作 
#### 下载太记
下载最新版本的TidGi（太记）： https://github.com/tiddly-gittly/TidGi-Desktop/releases

选择太记主要是因为不想再重头折腾Tiddlywiki了，太记相当于一个开箱即用库。
#### 添加工作区
点击左侧加号，
![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/202309042142326.png)
添加一个工作区
![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/202309042143432.png)
#### 配置工作区
因为该插件提到

> TidGi v0.8.0 需要在工作区设置 博客和服务器设置中 启用 HTTP API 并 关闭 凭证鉴权选项。

所以右键工作区，配置工作区，
![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/202309042146597.png)

点击`博客和服务器设置`右边的箭头（仔细看一下这箭头，我一开始就没看到，以为全部展开），然后开启HTTP API，关闭凭证鉴权。
![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/202309042148810.png)

#### 安装插件
进入控制台（齿轮状按钮）-插件-获取更多插件
![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/202309042150815.png)

选择`太微中文社区插件源(大陆加速版)`，在插件库中检索Obsidian，找到发布工具插件，安装后关闭。

![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/202309042152455.png)

然后右键工作区，重启服务，

![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/202309042153703.png)

#### 导入ob库
重启后，进入控制台，插件，找到Obsidian插件，可用Ctrl+F进行检索。

![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/202309042155630.png)

点击下拉按钮，输入ob库所在的文件夹路径，例如`D:\tiddlywiki\obsidian`。点击Add按钮，等待一会，就完成导入。

![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/202309042157458.png)

完成导入后，在你太记文件夹中的tiddlers文件夹就有相关的ob文件。
![image.png](https://gitee.com/cyddgi/picture-store/raw/master/img/202309042158258.png)

# 有待改进的地方
因为Tiddlywiki的Markdown语法比较严格，也有ob语法不一致，导入后的显示存在不匹配，需要进一步加强。