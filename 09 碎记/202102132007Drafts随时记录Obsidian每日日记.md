本文由[[Mr。麦]]撰写并授权于ob教程内发表。
原文发表地址：https://www.geekmai.top/archives/20 。
作者署名：麦先生。

---

![](https://static.geekmai.top/uPic/20210213122840.jpg)

## 使用场景
Drafts作为纯粹的草稿软件，更适合碎片化、无需整理的记录，这其实与我使用Obsidian中的DailyNotes的方法是一致的「流水账式的记录当日的想法」。但Obsidian目前只有桌面端，在移动端目前还没有很好的解决方案，从Obsidian的QQ群友@Boninall那里习得了Drafts与Obsidian联动的方法，经过改进后形成了现在的使用方法。

## 使用效果
在Drafts中随意记录后使用Action一键将内容增加到Obsidian中的当日笔记中（如果没有则会创建当日笔记）。

## 设置方法
使用坚果云或其他同步盘将Obsidian的库同步至云端，我使用的是坚果云，这里就以坚果云为例，详细设置方法如下：

在Drafts中新建Action
点击Drafts右上角的图标→打开动作管理页面→点击右下角的+号→选择New Action

![](https://static.geekmai.top/uPic/20210213114425.png)

在Identification中填写动作名称，这里以灵感日记为例

![](https://static.geekmai.top/uPic/20210213114432.jpeg)

点击Steps中的0 steps打开step管理页面，点击右上角的+号来新增一个step

![](https://static.geekmai.top/uPic/20210213114436.png)

选择Services分类下的WebDAV，这里说明一下，如果你使用的是OneDrive或GoogleDrive同步的Obsidian库，则选则相应的即可。

![](https://static.geekmai.top/uPic/20210213114441.png)

在File一栏中，将name设置成`[[date]].md` 

![](https://static.geekmai.top/uPic/20210213114445.png)

这里需要注意将Obsidian中的日记的文件名格式改为`YYYY-MM-DD` 

![](https://static.geekmai.top/uPic/20210213114450.jpg)

path中填入你的Obsidian库的相对于云端根目录的路经，比如我的每日笔记的路径是这样的

![](https://static.geekmai.top/uPic/20210213114454.jpg)

那么在path中填入`/麦麦/250 - 写作/Notes/010 - Daily`

Template中，在`[[draft]]`的上面增加一个空行，目的是为了将新增的内容与每日笔记中原有的内容之间增加一个空行。注：[[draft]]变量存储的是将你在drafts中写的所有内容。

![](https://static.geekmai.top/uPic/20210213114458.png)

write type中，选择`append`，这里解释一下4种写入类型
-   **create**：创建一个新文件。如果该位置已存在现有文件，请创建新文件并添加数字后缀。
-   **replace**：创建新文件，如果存在则覆盖现有文件。
-   **prepend**：在文件开头添加模板内容。如果文件不存在，请创建它。
-   **append**：将模板内容追加到文件末尾。如果文件不存在，请创建它。

点击右上角的save&exit退出即可

第一次运行该动作的时候，drafts会要求获得相关软件的授权，比如WedDAV同步方式需要获取坚果云的授权。

打开坚果云网页端→右上角用户名→用户信息→安全选项→第三方应用管理→添加应用→输入Drafts→点击生成密码

![](https://static.geekmai.top/uPic/20210213114501.jpg)

服务器地址和账户见示例，密码就是刚才生成的密码

![](https://static.geekmai.top/uPic/20210213114506.jpg)

将以上三项填入Drafts中即可

到这里，我们就可以愉快地在手机上随时记录每日笔记咯～