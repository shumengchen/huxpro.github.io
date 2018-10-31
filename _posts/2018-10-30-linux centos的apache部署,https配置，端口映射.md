---
layout: post
title: "linux（cnetos）的apache部署，https配置，和端口映射"
subtitle: 'Apache deployment of Linux (cnetos), SSL configuration, and domain mapping'
author: "书蒙尘"
header-style: text
tags:
  - linux
  - centos
  - apache
  - SSL
  - https
  - 域名
---

今天终于花了一天的时间终于在github上部署了第一个自己的个人博客，用的是[hux的个人博客]（https://github.com/Huxpro/huxpro.github.io）的主题，本来想在自己服务器上搭的，最后只先在github上搭进行使用了。

---

先去这个[https://github.com/Huxpro/huxpro.github.io]( https://github.com/Huxpro/huxpro.github.io)上fork到自己的github上面，把工程名修改为{github-username}.github.io，类似![img](/img/201810/githubName.png)，这个配置完就能通过{github-username}.github.io或者{github-username}.github.io/index来访问你的博客，可能不会立即生效。

为了让个人博客看起来有自己的标志，可以注册一个域名，当然要进行备案，我是在*腾讯云申请的域名*，[smchen.xyz](https://smchen.xyz)。

1、把域名设置成指定域名到{github-username}.github.io上。

2、在github项目的settings的gitHub page中输入你的域名![img](/img/201810/githubPage.png)
 
 这样个人博客就搭好了。