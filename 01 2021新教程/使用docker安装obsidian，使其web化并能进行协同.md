---
uid: 20221106164921
aliases: []
---
作者自述可见： https://zhuanlan.zhihu.com/p/581414249

本文分为两部分，第一部分是我使用的心得，第二部分是宏沉一笑的部署教程（已获转载）。
# 本人的话
今天宏沉一笑分享了一个obsidian的docker镜像。这个ob的docker化项目之前我也听说过，但当时好像是无法进行中文输入，一笑的镜像目前是可以使用了，并且比较容易部署，但对不了解docker和vps的用户还是有较高的门槛。

本人也不是很了解这些内容，有问题请到该项目页留言询问： https://github.com/WHG555/obsidian-docker 。

## 安装时我遇到的问题
下文中我说的安装命令是指
```
docker run -v /data/vaults:/vaults -v /data/config:/config -p 526:22 -p 6816:6080 -p 6818:6090 -p 5926:5900 -p 27123:27123 -p 27124:27124 --rm --device /dev/fuse --privileged obsidian-docker:v1.0
```

我按照教程，拉取了镜像， 但在安装时，docker查无此镜像，我最后是通过指定镜像ID的方式安装上了。相关的代码是`docker images`，然后把查询到的ID，替换教程安装步骤中`obsidian-docker:v1.0`。

我目前在VPS上有运行Syncthing，这样就可以连通VPS、PC、手机这三者，我之前也写了相关文档[[使用腾讯云搭建Syncthing来同步obsidian by 软通达]]。这可能要修改docker安装命令中的映射文件夹位置，即语句`-v /data/vaults:/vaults`。

## ob的协同
许多的ob用户都在考虑能否进行协同操作，这个在之前的Q群中也有多次的探讨。这个docker镜像使之成为可能。

我尝试了多浏览器同时登陆这个地址，都可以进行（见下图），这样就可以让多人同时编辑一个ob库。但具体协同的方法还需要未来的细化，例如syncthing在vps端可以设置为仅发送，其他端设置为仅接受。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/202211061706147.png)




# 以下为宏沉一笑撰写的教程
## 说明文档
github库：https://github.com/WHG555/obsidian-docker

## obsidian-docker
在docker中安装了obsidian，可以部署在服务器上，通过网页进行访问

## 下载
>docker pull 1002285542/obsidian-docker:v1.0
>https://www.123pan.com/s/vORrVv-4Iuqh提取码:E1my
# 使用
前台使用
>docker run -v /data/vaults:/vaults -v /data/config:/config -p 526:22 -p 6816:6080 -p 6818:6090 -p 5926:5900 -p 27123:27123 -p 27124:27124 --rm --device /dev/fuse --privileged obsidian-docker:v1.0

后台使用
>docker run -d -v /data/vaults:/vaults -v /data/config:/config -p 526:22 -p 6816:6080 -p 6818:6090 -p 5926:5900 -p 27123:27123 -p 27124:27124 --device /dev/fuse --privileged obsidian-docker


## 密码                                                         中文输入
VNC端口：5926  密码：123456

[https://192.168.55.25:6818/vnc.html](https://192.168.55.25:6818/vnc.html)

网页端口：6818   密码：123456

## 编译
>docker build -t obsidian-docker .