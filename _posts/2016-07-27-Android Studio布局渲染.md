---
layout: post
title: Android studio布局加载器异常
tags:
- Android Studio
- 布局渲染
categories: Android
description: Android studio布局加载器异常
---

## Android studio布局加载器异常

我们有时候会因为种种原因遇到这样的情况：

![这里写图片描述](http://img.blog.csdn.net/20160407144550562)

点击Details可以看到错误的详细信息：

![这里写图片描述](http://img.blog.csdn.net/20160407144632438)

这通常是Android Studio的布局加载器发生异常，渲染图形失败。一般可能是刚升过SDK，而你的工程还是较低的版本，当布局加载器用港更好的SDK版本渲染就会出现SDK与布局加载器不兼容的问题，解决办法很简单，选择低版本的SDK即可：

- 在XML文件中由text进入Design：
 
 ![这里写图片描述](http://img.blog.csdn.net/20160407144733532)
 
- 	点击上边的安卓小人，进行选择：

![这里写图片描述](http://img.blog.csdn.net/20160407144805360)

- 	最后切换到text中，就可以看到错误已经解决啦！

![这里写图片描述](http://img.blog.csdn.net/20160407144831298)

开始你的编程之旅吧