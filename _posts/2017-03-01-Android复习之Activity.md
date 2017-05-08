---
layout: post
title: Android简单复习之Activity
tags:
- Android复习
categories: AndroidReview
description: Android简单复习之Activity以及Activity的跳转
---
#Android简单复习之Activity

这次我们来简单复习一下Android的四大组件中的**Activity**

**Activity**是一个应用程序组件，提供用户与程序交互的界面，


Activity不仅为我们呈现了整洁的界面还让我们可以与应用程序有着数不清的联系，可以告诉程序我们想要做什么	

##Activity的创建使用

* 首先继承Android的Activity类
* 重写onCreate的方法，并调用setContentView方法
* 通过setContentView设置显示布局
* 最后在AndroidManifest文件中注册Activity

*代码如下：*

```
 public class MainActivity extends Activity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}

```

在AndroidManifest文件中有activity的标签，可以看到在activity中有个name，
`android:name=".MainActivity"`
> 这里面name的组成可以是“`.+Activity的名`”，也可以是“`Activity的包名+.+Activity的名`”

如果这个Activity是主入口，那么我们还需要设置**action**和**category**

*代码如下：*

```
<activity android:name=".MainActivity" >
      <intent-filter>
         <action android:name="android.intent.action.MAIN" />

          <category android:name="android.intent.category.LAUNCHER" />
      </intent-filter>
 </activity>
 
```
##Activity的生命周期

Activity的生命周期就是Activity从创建到销毁的一个过程，仿佛我们人从出生到死亡一样。

**生命周期的方法：**

* onCreate();创建
* onStart();运行
* onResume();获取焦点
* onPause();失去焦点
* onStop();暂停
* onDestroy();销毁
* onRestart();重运行

**一个Activity的多种变化形式：**

* 从无到有创建一个Activity
* 当前的Activity失去焦点
* 从当前的Activity跳转到另一个Activity
* 当前Activity被置入后台

###从创建一个Activity到销毁的生命周期

一个Activity刚创建时候的生命周期：

>onCreate() ——> onStart() ——> onResume()

Activity从创建到销毁的生命周期：
>onCreate() ——> onStart() ——> onResume() ——>onPause() ——> onStop() ——> onDestroy()

Activity从启动到失去焦点生命周期：
>onCreate() ——> onStart() ——> onResume() ——> onPause()

Activity从启动到失去焦点，再到获取焦点的生命周期：
>onCreate() ——> onStart() ——> onResume() ——> onPause() ——> onResume()

Activity从启动到后台的生命周期：
>onCreate() ——> onStart() ——> onResume() ——> onPause() ——>onStop()

Activity从启动到后台，再到前台的生命周期：
>onCreate() ——> onStart() ——> onResume() ——> onPause() ——> onStop() ——> onRestart() ——> onStart() ——>onResume()

###Activity的跳转

关于Activity的跳转使用的是Intent，我之前写过一篇文章，可以进行参考
[Activity页面跳转](https://dapengyou.github.io/android/2016/07/26/activity页面跳转)










