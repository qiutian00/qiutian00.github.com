---
layout: post
title: AndroidManifest.xml的配置
tags:
- AndroidManifest.xml
categories: IDE
description: AndroidManifest.xml的配置
---
## AndroidManifest.xml的配置
 

## 1.1全局配置
全局配置里面包括两点：

- 应用的报名以及版本信息的管理
- 控制android版本信息

1.应用的包名以及版本信息的管理：

```
  <manifest
   package="com.example.ladyZhou"
   android.versionCode="1"
   android.versionName="1.0" >
```
  package是你工程建的包，versionCode是你工程的版本号
  
2.控制android版本信息:

```
	<uses-sdk   
		android:minSdkVersion="16"
		android:targetSdkVersion="23" />
```
其中minSdkVersion是可以支持的最低系统版本，targetSdkVersion是你期望系统支持的版本。

## 1.2组件配置
Android的构成基石是四大组件，分别是：

- Activity(活动)
- Service(服务)
- Content Provider(内容提供者)
- Broadcast Receiver(广播接收者)

1.Activity配置

```
  <activity android:name="com.ladyzhou.MainActivity">
      <intent-filter>
         <action android:name="android.intent.action.MAIN" />
		 <category android:name="android.intent.category.LAUNCHER" />
      </intent-filter>
  </activity>
```
当你新建了一个活动时，必须要在AndroidManifest.xml文件中注册Activity信息，否则你的程序就会抛出异常，*如果你的代码都没有错那么就来这找找原因吧*

此外

```
 <intent-filter>
         <action android:name="android.intent.action.MAIN" />
		 <category android:name="android.intent.category.LAUNCHER" />
      </intent-filter>
```
这个部分是相当于一个程序入口Activity

2.Service配置

```
<service android:name="com.ladyzhou.service.CouponService" >
	 <intent-filter>
	 	<action android:name="com.ladyzhou.service"
	 </intent-filter>
</service>
```
Service与Activity的区别是：Activity是用于界面而Service是后台的逻辑代码的处理

3.Content Provider配置

ContentProvider用来管理数据哭访问以及程序内和程序间的数据共享

```
	<provider android:name="com.ladyzhou.manifest.provider" >
	</provider>
```

4.Broadcast Receiver配置

```
<receiver android:name="com.ladyzhou.receiver.InstallReceiver" >
	 <intent-filter>
	 	<action android:name="ladyzhou.app.install"
	 </intent-filter>
</receiver>
```

## 1.3权限配置

一个程序在安装前会提醒你这样那样的权限，其中包括短息权限、位置权限、相机权限等等，下面我们来看看这些权限在配置文件中如何声明

1.系统权限配置

```
	<uses-permisssion android:name="android.permission.INTERNET" />
```
这里的权限设置根据你的需要查找系统所提供的权限选择

2.自定义权限配置

```
	<uses-permisssion android:name="ladyzhou.permission.ENDACTIVITY" />
```
这里的自定义权限可以自定义命名，用以保护android的某些重要组件

AndroidManifest.xml配置的简单介绍就到这里了！！！
