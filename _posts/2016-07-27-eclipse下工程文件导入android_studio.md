---
layout: post
title: Eclipse下工程文件导入Android Studio
tags:
- Android Studio
- Eclipse
categories: IDE
description: Eclipse下工程文件导入Android Studio
---

## Eclipse下工程文件导入Android Studio
- 很高兴和大家再次见面，我是lady_zhou，这是我的Blog，欢迎大家一起来学习Eclipse下工程文件导入Android Studio


现在Android Studio已经被大部分人使用，Eclipse即将退出历史舞台，但是有一个问题，就是原先在Eclipse下编写的工程要怎么办？当然是导入Android Studio里面咯！下面来介绍一下Eclipse下的工程导出和Android studio的工程导入：

#### Eclipse的工程导出

1. File-->Export..

   ![这里写图片描述](http://img.blog.csdn.net/20160408142518604)

2. 选择Android文件夹下的第二个

   ![这里写图片描述](http://img.blog.csdn.net/20160408142211693)

3. 点击Next，遇到让你选择的文件夹时，选择你想导出的文件夹即可，继续点击Next



4. 当遇到下面这个界面的时候记得打勾，然后继续Next-->finish

	![这里写图片描述](http://img.blog.csdn.net/20160408142640355)

这样文件就导出成功了，到你该工程的所在路径下你会发现工程会有些许的变化


#### Android studio导入工程

一般在AS下创建的工程点击**open**找到该工程就可以了，但是如果你要导Eclipse 导出的工程就不能这样选择打开了

1. 你要将你的所有工程都关闭，进入这样的界面
	
	![这里写图片描述](http://img.blog.csdn.net/20160408142753027)

2. 选择第四个，点击，找到你要导入的工程就可以了
3. 接下来你的工作就是选择相应的SDK就可以了

一般在Eclipse和AS中配的SDK路径是一样的，所以在选择SDK版本的时候不会出太大的问Eclipse下工程文件导入Android Studio题