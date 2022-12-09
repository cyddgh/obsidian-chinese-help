---
uid: 20221120162646
aliases: []
---
obsdiain本身是基于Electron框架开发的，本身对网页的兼容性就不错。Web browser插件利用了这一特性，才能以不足100kb的代码让ob成为一个网页的浏览器。

# 插件名片
本文所介绍的Web browser插件，是由Bon接手后开发的分支，其项目地址为： https://github.com/Quorafind/obsidian-web-browser 。该项目的原作者是Trikzon，初始项目地址为 https://github.com/Trikzon/obsidian-web-browser 。

需要注意，目前的插件还处于开发的初期，一些设置后期可能有所变化。目前，启动插件后，没有任何设置界面，也不在命令模式中。

# 实际操作
##  基础功能
目前插件的使用非常简单，点击标签栏最右边的New tab，开始新的标签页。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202211201706960.png)


注意多了一个地址栏，可以在这里输入网址。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202211201707314.png)


最后的效果
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202211201708186.png)

并且，在安装插件后，在ob中新点击网页链接，也将在ob的新标签页访问该地址，而不是使用系统的浏览器打开。

## 可能的功能
该插件为ob的使用提供了更大的可能，有许多值得探索的空间。例如，我最近使用了简悦进行网页剪藏，将网页变成了本地的html，该插件可以使得ob可以去访问这些html。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/202211201723052.png)

而且，在本插件中可以实现目前浏览器中常见的“复制跳转高亮功能”（我真不知道该功能的术语，就是在网页中划选一段文件，右键后有一复制功能），在目前ob浏览器插件中为“Copy Hightlight link”，在Edge中为“复制指向突出显示的链接”。这样就对网页上的内容在字句层面进行引用，对于文献阅读等，应该是有帮助的。该功能曾经也被一个双链软件（目前已停运了？）认为是独有的功能。

例如，点击`http://127.0.0.1:4000/#:~:text=%E8%BD%AF%E4%BB%B6%E6%94%B9%E5%96%84%E7%94%9F%E6%B4%BB` （仅在我的电脑上），能出现以下效果。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/202211201725193.png)



