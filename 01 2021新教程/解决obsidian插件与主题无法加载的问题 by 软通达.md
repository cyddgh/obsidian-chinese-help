---
title: 
uid: 202012182133
aliases: []
tags: []
from: 
---
[[软通达]]

# 引言

本文的判断obsidian插件和主题无法加载的前提有以下3点

1. obsidian插件和主题是位于raw.githubcontent.com

2. 因为种种问题可能无法访问Github

3. 我们可以通过修改hosts文件来解决第2点的问题

  

基于以上3点，我撰写了本文。如果认识有误或未来以上3点有变，本文的解决方法可能失去效力。

  

本文的解决方案是基于521xueweihan给出的方案（https://github.com/521xueweihan/GitHub520 ）。因为手头没有Mac电脑，本文仅针对windows，但道理互通。

  
  
  

# 修改Hosts

有多种方式能修改Hosts文件：

1. 在windows系统中，按住键盘的“windows键+R键”，弹出运行框。在运行框内输入“notepad %SystemRoot%\system32\drivers\etc\hosts”（注意没有上下引号，下同）。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201218215934.png)

就直接回弹出一个记事本，如果完成可以跳转到下一标题。

  

2. 在windows界面左下角右键，点击“运行”，弹出运行框。在运行框内输入“notepad %SystemRoot%\system32\drivers\etc\hosts”

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201218215531.png)

就直接回弹出一个记事本，如果完成可以跳转到下一标题。

  

3. 进入资源管理器，在地址栏内输入“C:\Windows\System32\drivers\etc”，找到hosts文件，右键，点击打开方式

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201218220422.png)

在列表中选择记事本，点击确认。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201218220539.png)

  

# 在hosts中添加信息

在弹出的记事本末尾，将下列信息复制过去（以下信息来自于https://github.com/521xueweihan/GitHub520 ，有时效性，请及时确认更新），记事本中原有的文件不必改动，然后保存。

```

# GitHub520 Host Start

185.199.108.154 github.githubassets.com

199.232.96.133 camo.githubusercontent.com

199.232.96.133 github.map.fastly.net

199.232.69.194 github.global.ssl.fastly.net

140.82.114.3 gist.github.com

185.199.108.153 github.io

140.82.113.4 github.com

140.82.114.5 api.github.com

199.232.96.133 raw.githubusercontent.com

199.232.96.133 user-images.githubusercontent.com

199.232.96.133 favicons.githubusercontent.com

199.232.96.133 avatars5.githubusercontent.com

199.232.96.133 avatars4.githubusercontent.com

199.232.96.133 avatars3.githubusercontent.com

199.232.96.133 avatars2.githubusercontent.com

199.232.28.133 avatars1.githubusercontent.com

199.232.96.133 avatars0.githubusercontent.com

140.82.112.9 codeload.github.com

52.216.128.147 github-cloud.s3.amazonaws.com

52.217.8.100 github-com.s3.amazonaws.com

52.216.107.188 github-production-release-asset-2e65be.s3.amazonaws.com

52.217.17.148 github-production-user-asset-6210df.s3.amazonaws.com

52.216.9.75 github-production-repository-file-5c1aeb.s3.amazonaws.com

# Star me GitHub url: https://github.com/521xueweihan/GitHub520

# GitHub520 Host End

```

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201218220839.png)

  

# 刷新DNS

按步骤1的方法，在运行框中输入“ipconfig /flushdns”，点击确认，就完成了本教程。如果还无法访问obsidian插件和主题，可以重启一下电脑。

![](https://gitee.com/cyddgi/picture-store/raw/master/img/20201218221037.png)