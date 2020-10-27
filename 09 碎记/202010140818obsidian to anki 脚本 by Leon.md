[[如何与anki连用]] [[重点文章]]
[[Leon]]进一步解释了[[202010051820Obsdian to Anki 脚本使用 by Leon]]并且截图了。目前的存放位置在[Github](https://github.com/cyddgh/obsidian-anki-By-Leno)或[Gitee](https://gitee.com/cyddgi/obsidian-anki-By-Leno)。

[[Leon]]：新建了个虚拟机，从头装了一次obsidian to anki 脚本， 基本全程截图了
我自己碰到的主要问题是
obstoanki_setup.py安装依赖时出错，查了后卸载Python3.9换成旧版本3.8.6就可以
用Node.js最新版也会自动安装Python3.9，我是运气好第一装Node.js装的是lts长期支持版，那个给我装的python是3.8.6的
昨天的录屏误导性太大，我删掉了。实体机上装的软件太多，重新演示没碰到坑一闪而过了；虚拟机全新安装碰到一堆坑，折腾了将近4个小时......

[[LewisNepenthes,]]：安装教程里面给的python直链安装包虽然名字是3.8.6，但实际下载下来仍然还是3.9.0，教程中的图片也得到了印证，看到的话记得改一下链接和图片~
这个是python3.8.6的直链安装包，https://www.python.org/ftp/python/3.8.6/python-3.8.6-amd64.exe
另外确实如教程所说，装Ob2Anki这个脚本，会遇到的一个大问题，就是因python版本不同而导致某些依赖装不上，具体来说就是pillow和wxpython，卸载了python3.9.0重新装上3.8.6后，问题立马迎刃而解，再次感谢！