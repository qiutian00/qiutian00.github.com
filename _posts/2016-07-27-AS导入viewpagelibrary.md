---
layout: post
title: Android studio导入viewPagerlibrary
tags:
- Android Studio
categories: IDE
description: Android studio导入viewPagerlibrary
---

## Android studio导入viewPagerlibrary

- 很高兴和大家再次见面，我是lady_zhou，这是我的Blog，欢迎大家一起来学习Android studio导入viewPagerlibrary


####想写出这样的界面效果就得用到Fragment，ViewPagerIndicator

![](http://img.blog.csdn.net/20140412094426906)

那么问题来了，利用开源控件ViewPagerIndicator实现Tab，就得导入相应的library文件


[Github下载](https://github.com/JakeWharton/Android-ViewPagerIndicator)

还可以去鸿洋大神的博客去下载，这篇博客介绍了实现这种界面效果的方法，里面有源代码可以下载：
 
 [博客](http://blog.csdn.net/lmj623565791/article/details/23513993)
 
 我是下载的博客里的源代码，viewPagerlibrary这个文件夹是你要导入library，下面来介绍在**Mac os x下Android studio**的导入：
 
 1.在最顶层的**build.gradle文件中**（也就是在你建的工程下的**build.gradle文件中**）添加两行代码：
 
 	maven { url "http://dl.bintray.com/populov/maven" }
 
 	mavenCentral()
 
 添加后build.gradle文件中的代码大致是这个样子：
 
 
 ```
 buildscript {
    repositories {
        maven { url "http://dl.bintray.com/populov/maven" }
        mavenCentral()
    }
 }

allprojects {
    repositories {
        maven { url "http://dl.bintray.com/populov/maven" }
        mavenCentral()
    }
}
 
 ```
 
 2.在app文件夹下的build.gradle文件中添加代码：
 	
 	compile 'com.viewpagerindicator:library:2.4.1'
 	
 添加后build.gradle文件中的代码大致是这个样子：
 
 ```
 dependencies {
    compile fileTree(dir: 'libs', include: ['*.jar'])
    testCompile 'junit:junit:4.12'
    compile 'com.viewpagerindicator:library:2.4.1'
    compile 'com.android.support:appcompat-v7:23.2.1'
    
 ```
  
 3.当你做完上面两步后，这时候就该使用你下载好的viewPagerlibrary文件，（这里的文件是以Eclipse写的，最好在eclipse中将viewPagerlibrary文件导出放入AS中），导出和引入步骤可见我的博客：
 
 [Eclipse下的工程导入Android studio中](http://blog.csdn.net/lady_zhou/article/details/51096522)
 
 
 **导入viewPagerlibrary**步骤：（好像不做也可以）
  
1. File——>project structure，进入后点击**＋**号：
 
 	![这里写图片描述](http://img.blog.csdn.net/20160408144058358)
 	
2. 选择Import Gradle Project:
 
 	![这里写图片描述](http://img.blog.csdn.net/20160408144408145)
 
3. 选择viewPagerlibrary的路径：
 
 	![这里写图片描述](http://img.blog.csdn.net/20160408144626085)
 
4. 一路next，就导好了，代码中错的地方就可以引包了
 
5. 一定有人再导入library后还进行了这一步操作：
 
 
 这样做，代码中的错的地方会自动引包，但运行的时候会出现：
 
  ![这里写图片描述](http://img.blog.csdn.net/20160408144500990)
 
 这就是有重复的包了，需要删掉一个，主要冲突的包是android－supper－v4包，所以做到第四步就可以了，如果你做了第五步，那你就点击第五步的**－**号，移除viewPagerlibrary，运行如果该是报错，删掉viewPagerlibrary下lib文件夹下的android－supper－v4包就可以了，系统会关联默认的android－supper－v4包
 
#### 下面来介绍在**Eclipse**的导入
 
 具体步骤右键library——properties——Java Build Path——order and export，找到冲突jar包，如果没有找到Android Private Libraries,将前面的勾勾取消，再编译运行就可以了