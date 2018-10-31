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

最新在弄一个小程序https合法域名，搞了一天，发现这是一个麻烦的过程，配置过程中遇到很多麻烦，在这里记录一下，保存自己的配置过程。

我是基于centos系统进行配置，首先先安装apache：

> // 安装httpd
[root@VM_0_17_centos ~]# yum install httpd -y

> // 查看httpd版本
[root@VM_0_17_centos ~]# httpd -v
Server version: Apache/2.4.6 (CentOS)
Server built:   Jun 27 2018 13:48:59

> // 启动httpd
[root@VM_0_17_centos ~]# service httpd start
Redirecting to /bin/systemctl start httpd.service

请求你的服务器ip地址如果访问到![img](/img/201810/apache.png)就安装成功了

---

SSL配置：可以到阿里云或者腾讯云申请免费的SSL证书，我的证书是在腾讯云申请的，证书通过后下载有解压在Apache中有三个文件![img](/img/201810/SSL.png),这三个文件待会要用



> //安装mod_ssl 
[root@VM_0_17_centos /]# yum install mod_ssl
//安装完后会在/etc/httpd/conf.d下生成ssl.conf文件

> //在/etc/httpd下创建ssl文件
[root@VM_0_17_centos httpd]# mkdir ssl
//把刚刚ssl证书的三个文件放入这个文件夹，修改conf.d下的ssl.conf
[root@VM_0_17_centos conf.d]# vim ssl.conf

![img](/img/201810/sslConf.png)
访问地址，把前面的http改为https，还能访问到页面配置成功了

---
为服务器配置域名，再通过 https://域名 访问到apache

---
配置端口映射，访问其他端口工程
httpd的conf文件下的httpd.conf末尾处添加这些，就可以在通过 https://域名/blog 访问这个8080端口的项目了

> ProxyPass  /blog http://IP:8080
ProxyPassReverse  /blog http://IP:8080