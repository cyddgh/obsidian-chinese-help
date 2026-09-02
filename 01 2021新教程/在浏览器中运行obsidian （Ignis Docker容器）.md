# 摘要
使用Docker中的Ignis容器，可以在VPS服务器或者NAS上部署obsidian，用反向代理在公网获得访问，使得我们可以获得一个随时在线的obsidian软件。
# 引言
在obsidian使用中，同步是一个大家一直讨论的问题。但如果一直都是使用一个obsidian的库，就不存在同步的需要了（但记得备份）。最近看到一些推文，介绍了Docker中的Ignis容器，可以使得我们在VPS服务器上部署obsidian。这样还能解决一些ob无法使用的问题：例如老旧电脑无法安装最新版本的ob、一些公司电脑禁止安装个人软件。
我参考是各种折腾（杨浦老苏）的推文 https://mp.weixin.qq.com/s/8UGn3TvvI14CgcvaboD_VQ ，然后让AI整理后，在线上部署成功了。但这操作一般需要你了解Docker的部署和反向代理，还需要你有一台服务器、一个域名，需要一定的技术门槛。

# 实际操作
操作的过程可见上面的推文。我分享一下我的Docker yaml

```
services:
  ignis:
    image: nobbe/ignis:0.8.10
    container_name: ignis
    restart: unless-stopped
    ports:
      # 仅供本机反向代理访问；不要在腾讯云安全组中开放 8314。
      - "127.0.0.1:8314:8080"
    environment:
      # VPS 的 用户 UID/GID（已确认）。
      PUID: "1001"
      PGID: "1001"
      # 使用手动上传的 Obsidian 安装包，不在首次启动时下载。
      OBSIDIAN_PACKAGE: /packages/obsidian.deb
    volumes:
      # Vault、Ignis 配置和 Obsidian 应用缓存均持久化在宿主机。
      - /home/opsadmin/docker/ignis/vaults:/vaults
      - /home/opsadmin/docker/ignis/data:/app/data
      - /home/opsadmin/docker/ignis/app:/app/obsidian-app
      # 请上传官方 Obsidian 1.12.7 的 Linux AMD64 .deb 至此路径。
      - /home/opsadmin/docker/ignis/obsidian.deb:/packages/obsidian.deb:ro

```

需要注意到是，现在ob官网的安装包是1.13.7，1.12.7的文件可以从 https://github.com/obsidianmd/obsidian-releases/releases/download/v1.12.7/obsidian_1.12.7_amd64.deb 中下载。

安装完毕后，记得在反向代理设置中开启密码验证，因为发布到公网后，网页是未加密的状态。
# 使用效果
部署成功后，在浏览器中的效果如下，我也安装成功了Task Genius插件和坚果云的同步插件，都可以正常运行。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/2026/202609/20260901220559824.png)

在手机浏览器上的效果如下：
![9b75e4037f5ff79b4a017dc262195d07.jpg](https://gitee.com/cyddgi/picture-store/raw/master/img/2026/202609/20260901220915696.png)

因为都是共用一套数据，所以也无需同步，或者也可以同步后，在手机的ob中打开。

# 其他的话
不知道现在ob的同步服务是用什么插件，最近也看到一些推文但也没尝试？另外，任务管理插件大家有什么推荐吗，除了Task Genius插件外，Tasks插件似乎也很受欢迎。

为什么我要在线上部署这个ob呢，原因有以下两点：
第一，今年没续费滴答清单，需要一个有日历视图的好用的GTD软件，首先想到的就是bon佬的Task Genius。
第二，现在服务器上还运行着Hermes，现在Agent收集的材料可以保存成md，如果云端上有一个ob，也方便我查看。