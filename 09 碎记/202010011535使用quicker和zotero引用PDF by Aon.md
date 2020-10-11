[[Leon]]介绍了一个[[quicker]]和[[zotero]]引用PDF的动作
https://getquicker.net/Sharedaction?code=3eac1c7e-1f57-4146-4ddc-08d85ac8eddb
其他核心软件：zotero
而且可以跟obsdian_to_anki脚本完美配合，转换的anki卡片也带跳转链接

这个动作比ABC动作方便的地方在于：1.不用在pdf文件中写时间戳；2.链接直点，不需要选中时间戳运行另一个动作 
缺点，主要是关于另外装的软件zotero
1.zotero入门可能要折腾下；
2.依赖zotero打开外链，zotero的bug他也有，这里坑了我好久；
3.开zotero再开pdf，速度没有直接开pdf快

obsidain to anki脚本我开始也没折腾清楚，后面发现关键就两个点：
1.python脚本，我是装node.js傻瓜设置，没碰到跟python相关的问题；
2.配置文件中，关于文本格式转换卡片的规则着重看下定义好

坑主要在zotero上，如果没有同步需求都用默认设置反而没问题；用了zotfile之类的附件管理插件把附件放到onedrive可能会有问题不好解决 ；第二个是goldendict的ctrl+c+c快捷键好像有冲突，虽然动作里没看到用这个快捷键，但是我把goldendict快捷键禁用就没事了

动作介绍说他是基于Zplusless的[[202008271407用Quicker引用PDF by Zplusless]]