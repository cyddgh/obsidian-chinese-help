---
title: 
uid: 202111132004
aliases: []
tags: []
from: 
---

预警：本文所提及操作属于高阶内容，涉及服务器配置、docker技术、网络安全等等内容。我本人也不是很了解，只勉强达到“会用”的程度，对过程的表述和理解可能有偏差，仅提供一种同步的思路。本文涉及到购买建议，请三思后行。本文仅代表我个人通过相关步骤，实现了使用腾讯云搭建Syncthing来同步obsidian的效果，不代表在任何情况（例如内网等）都能实现，不代表数据能足够安全等等，本人对因本文造成的损失概不负责。

# 背景介绍
obsidian早鸟价已经结束，同步服务的价格恢复到10美元（按月付）/8美元（按年付），超出了很多ob使用者的预期。在此背景下，使用者开始寻求一些ob第三方同步的方法，我这里也简单归纳一下：
- 坚果云：如果只是Win、MAC之间的同步，推荐使用。不推荐与[[FolderSync（同步软件）]]连用给手机端做同步，很多人都遇到问题，可能是因为坚果云对第三方API调用的限制。
- icloud：如果你的设备设计iOS（iPhone或iPAD），这是推荐的第三方同步方法，另一种能同步iOS的方法是[[Working copy]]，但难度很高，我没有尝试过，听说效果也不是很好。
- OneDrive：似乎可以和[[FolderSync（同步软件）]]连用给手机端同步，这可能要问Bon。但可能要考虑onedrive的网络问题和权限问题。我也不推荐该方法。
- Syncthing：一个开源的同步软件，本文主要使用的软件，也是[[shaosen]]、[[淳帅二代]]主推的软件，我本人也推荐使用此第三方软件，但对该软件的配置问题不是很懂（有问题请不要问我，我也不太清楚），大家可以去github上留言： https://github.com/syncthing/syncthing 。这软件现在已经有41.4K的加星（star）这是很惊人的数量，说明软件深得人心。

使用Syncthing同步有一个问题是，必须有一个设备保持24小时在线，才能保证数据一直是最新的（其实所有的同步都是这样，需要有一个服务24小时运行）。因此我想到要租一个服务器（24小时在线且联网的电脑）。我先咨询了腾讯云的云开发CloudBase，想要使用其来搭建Syncthing服务。但工程师说，云开发的机器只能搭配已经适配好的那几款软件，即使有一个github导入，也必须是导入那几个适配好的软件。因此，我认为的最简单的也是最便宜的方案无法成功。

但我也给内部人员提出了相应建议，希望能早日适配syncthing。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211113202457.png)

# 正文部分
## 购买服务器
今天刚好见到了双十一腾讯云在促销自家的服务器（这活动一年有几次，所以如果你不是在最近看到，可以等等优惠的价格），可以点击我的推广链接（ https://cloud.tencent.com/act/double11?spread_hash_key=7f140183941722f69697fc0aeb325df9  ）前往会场。在“爆品秒杀”一栏，可以找到一台2核4G的服务器，3年只要198（我买的是这个），下面其实还有一台1核2G的3年144，但不知道性能可不可以，但更便宜。如果在购买和使用中遇到问题，请联系腾讯云的工程师和售后人员，他们应该很乐意也有义务提供专业的协助。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211113203001.png)

点击购买后，镜像一栏选择docker，我无法截图了，因为这价格一人只能买一次。选错镜像也没关系，之后可以重置镜像，服务器不要选错就行。

## 宝塔面板的配置
购买后，到轻量应用服务器页面（ https://console.cloud.tencent.com/lighthouse ），上面的帮助文档可以选择“宝塔面板”的方便入门，点击“安装和配置宝塔 Linux 面板腾讯云专享版”（ https://cloud.tencent.com/document/product/1207/54078 ）先查看宝塔面板的配置文档，直接从文中“配置轻量应用服务器网络防火墙”一节开始看，安装文中的步骤操作。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211113203811.png)

点击“更多”-“管理”。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211113204032.png)

再点击“防火墙”-“添加规则”-创建两个规则，一个端口号是`8888`一个是`8384`（8888是宝塔的端口，8384是后面给syncthing预留的登陆端口），备注可不填写，其他选项不动。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211113204214.png)


![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211113204347.png)

之后的内容请根据“安装和配置宝塔 Linux 面板腾讯云专享版”（ https://cloud.tencent.com/document/product/1207/54078 ）的“配置宝塔 Linux 面板”操作。

## 登陆宝塔界面
配置好宝塔面板后，在浏览器输入`http://你的公网IP地址:8888/tencentcloud`，具体见“应用管理”一栏。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211113205144.png)


## 安装docker
点击宝塔页面左边的“软件商店”-检索“docker”-选择安装“Docker管理器 3.7”。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211113205304.png)

然后就会自动安装，等待安装结束。

参考“安装 Docker 并配置镜像加速源”（ https://cloud.tencent.com/document/product/1207/45596 ）一文，配置docker加速镜像。

但我是直接在桌面新建一个txt文件，输入以下代码，重命名为`daemon.json`，通过宝塔面包的“文件”，找到`/etc/docker/`这个地址，然后再将`daemon.json`上传。

```
{
"registry-mirrors": [
 "https://mirror.ccs.tencentyun.com"
]
}
```

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211113205903.png)


## 通过docker安装Syncthing
在服务器的界面（ https://console.cloud.tencent.com/lighthouse/ ）点击“登录”，进入到你服务器中开始输入代码（此步骤不唯一，但应该对新手最简单）。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211113210241.png)


之后会弹出一个黑色界面（类似命令提示符CMD），让你输入代码。

Docker的入门教程可以参考菜鸟出品的 https://www.runoob.com/docker/docker-hello-world.html  。

但我用不了那么多，我参考了“docker安装Syncthing，并配置数据同步备份” （ https://www.tqwba.com/x_d/jishu/190444.html ），这篇与CSDN上一篇很像（ https://blog.csdn.net/weixin_44395100/article/details/108233403 ），但CSDN无法复制代码，我就选择了前者。

首先，先输入`sudo docker`来验证docker是否安装成功，如果下面出现下面的界面就是成功的（没有报错，然后出来了一堆文字）。这样就可以开始按照上文来安装syncthing。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/20211113210835.png)

根据上文的代码，并在前面加上`sudo`，以获取最高权限，否则在该用户无法安装。即输入下面的代码：
`sudo docker run -d -p 8384:8384 -p 22000:22000 -v /users/syncthing:/var/syncthing syncthing/syncthing`

等待安装结束，文中的8384，就是之前在防火墙添加的8384，如果此处修改，防火墙那里的设置也要修改。

在你的浏览器中输入`http://你的公网IP地址:8384`，进入syncthing。之后就按正常操作配置syncthing，这已经有很多人论述，不在本文介绍范围内。

#### 202211031030对于vps设置的更新
本节内容感谢群友林克的指导。
目前我出于数据安全考虑，我是使用PC到手机的单向同步，又担心PC关机后，手机不能接受到最新的ob文档，所以又引入了VPS来完善这一流程。
基于上述的需求，我各设备对Syncthing的“文件夹类型”设置如下：
- PC：仅发送
- VPS：接受和发送
- 手机：接受和发送

![](https://gitee.com/cyddgi/picture-store/raw/master/img/202211031037300.png)

![](https://gitee.com/cyddgi/picture-store/raw/master/img/202211031038261.png)

如何出现了“撤销更改”的提醒，可以点击，使得其他端（VPS和手机）的更改都消失，保持和电脑端的数据一致。
![](https://gitee.com/cyddgi/picture-store/raw/master/img/202211031039453.png)