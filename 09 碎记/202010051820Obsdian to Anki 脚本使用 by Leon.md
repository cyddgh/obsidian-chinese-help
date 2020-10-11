[[Leon]] [[如何与anki连用]][[重点文章]]
## Obsdian to Anki 脚本使用
### 步骤简述
#### 1.环境准备：
1.1 python安装
1.2 双击一次obsidian_to_anki.py，会生成一个'obsidian_to_anki_config.ini'配置文件
1.3 修改配置文件，主要修改两项：一是转换的anki卡片放在哪个Deck库中，默认Default也可以不改；二是修改文本内容转换到anki卡片的映射规则。这里只描述多级标题作为问题、无标题作为答案的规则。
打开该配置文件，修改md文档转anki卡片的规则。
- 找到第60行，修改如下：
Basic = ^#+(.+)\n+((?:[^\n#][\n]?)+)
- 这个规则是针对多级标题做为问题，标题下面的无标题文本作为答案，具体参考[github关于映射规则说明](https://github.com/Pseudonium/Obsidian_to_Anki/blob/master/regex.md)

- 也可以直接下载我上传的配置覆盖。

1.4 Anki软件安装anki connect 插件并启用
#### 2.使用流程
2.1 anki软件保持在运行状态
2.2 双击obsidian_to_anki.py，勾选1,2,3，分别是扫描哪个目录、使用配置文件里的自定义映射规则、扫描子目录。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201005182310.png)
2.3 点start，自动同步。
#### 3.进阶
3.1 命令行
- 新建快捷方式，目标如下：
C:\Users\Leon\OneDrive\_ApplicationData\ObsdianLibrary\addon\obsidian_to_anki.py -d C:\Users\Leon\OneDrive\_ApplicationData\ObsdianLibrary\_Review -r -R
- '脚本路径' -d 'md文档目录路径' -r -R
- 参照github官网说明command line usage

3.2 配合Bon佬的摘录助手-限制版食用更佳。
3.3 还可以做计划任务全自动运行，这个我还没折腾
### 4. 可能的问题
4.1 Anki最好调成英文，脚本识别的模板是Basic，中文的话名字可能是基本
4.2 anki里面删除卡片的话，必须手动在md文档里也删除incline id,否则脚本后续会出错，就是这个样子的：

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201005182328.png)


问：Leon，这需要那个ini文件吗
答：不用，可以不用ini自己改的
只要打开自己的那个配置文件，修改一行就行，不用我上传的这个