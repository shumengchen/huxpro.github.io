---
layout: post
title: "centos7安装jdk8和maven,git安装"
subtitle: 'Centos7 installs jdk8 and maven,install git'
author: "书蒙尘"
header-style: text
tags:
  - jdk8
  - maven
---

服务器上配置jdk8，先到[https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)下载linux的jdk安装包。


> // 对jdk进行解压  
[root@VM_0_17_centos ~]# tar -zxvf jdk-8u191-linux-x64.tar.gz -C /usr/local/java

> // 打开配置文件  
[root@VM_0_17_centos java]# vim /etc/profile  

export JAVA_HOME=/usr/local/java/jdk1.8.0_191  
export JRE_HOME=${JAVA_HOME}/jre  
export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib  
export PATH=${JAVA_HOME}/bin:$PATH  

> // 使配置生效  
[root@VM_0_17_centos java]# source /etc/profile  
// 查看是否生效  
[root@VM_0_17_centos java]# java -version


---

安装maven

> //下载maven包  
[root@VM_0_17_centos ~]# wget http://mirrors.hust.edu.cn/apache/maven/maven-3/3.1.1/binaries/apache-maven-3.1.1-bin.tar.gz  
//解压到指定文件夹  
[root@VM_0_17_centos ~]# tar -zxvf apache-maven-3.1.1-bin.tar.gz -C /usr/local/maven3  
//配置环境变量  
[root@VM_0_17_centos maven3]# vim /etc/profile  
//使配置生效  
[root@VM_0_17_centos maven3]# source /etc/profile  
//查看mvn版本  
[root@VM_0_17_centos /]# mvn -v

配置文件中添加
export M2_HOME=/usr/local/maven3/apache-maven-3.1.1
export PATH=$PATH:$JAVA_HOME/bin:$M2_HOME/bin


---

安装git
>//通过yum安装git  
[root@VM_0_17_centos ~]# yum install -y git  
//查看git版本  
[root@VM_0_17_centos ~]# git --version
//配置ssh密钥，一直enter就好  
[root@VM_0_17_centos kiln]# ssh-keygen -t rsa -C "975952433@qq.com"  
//查看ssh  
[root@VM_0_17_centos kiln]# cd ~/.ssh/  
[root@VM_0_17_centos .ssh]# cat id_rsa.pub