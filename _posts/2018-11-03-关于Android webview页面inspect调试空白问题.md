---
layout: post
title: "关于Android，webview页面inspect调试空白问题"
subtitle: 'Apache deployment of Linux (centos), SSL configuration, and domain mapping'
author: "书蒙尘"
header-style: text
tags:
  - android
  - webview
  - inspect
---

android和html混合开发时，无法调试html页面，可以访问[chrome://inspect/#devices](chrome://inspect/#devices)，进行调试。


1、首先你要开起手机usb调试


2、程序以debug运行


若上面都已经弄好在页面中还是无法看到inspect按钮，可在代码中为webview配置
```js
//开启webview调试功能
if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.KITKAT){
    WebView.setWebContentsDebuggingEnabled(true);
}
```
就没问题了。