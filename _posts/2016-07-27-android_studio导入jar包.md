
---
layout: post
title: Android studio导入Jar包
tags:
- Android Studio
- 导入jar包
categories: IDE
description: Android studio导入Jar包
---
## Android studio导入Jar包

- 很高兴和大家再次见面，我是lady_zhou，这是我的Blog，欢迎大家一起来学习Android studio导入Jar包

有的时候编写程序会用到一些框架或者一些JAR包，下面就以Volly为例，介绍一下AS如何导入JAR包


AS导入JAR包很简单只需**三步**就轻松搞定：

 1. File-->Project Structure,点击**＋**号
	
	![这里写图片描述](http://img.blog.csdn.net/20160408182452714)


 2. 选择Impport .JAR/.AAR Package,点击Next，选择需要导入的JAR路径，点击Finish

	![这里写图片描述](http://img.blog.csdn.net/20160408182559292)
	
	![这里写图片描述](http://img.blog.csdn.net/20160408182616339)

 3. File-->Project Structure，点击app，根据下图来做：
 
 	![这里写图片描述](http://img.blog.csdn.net/20160408182707464)
 
 这样Volley的JAR包就导好了，不要忘记在使用Volley时，在AndroidManiFest.xml文件中添加这句话：
 
 	<uses-permission android:name="android.permission.INTERNET" />
 	
 不然会报错的