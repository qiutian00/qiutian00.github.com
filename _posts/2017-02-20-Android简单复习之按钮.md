---
layout: post
title: Android控件复习之---按钮
tags:
- Android复习
categories: AndroidReview
description: Android的控件复习之按钮
---
#Android控件复习之---按钮

Android中的按钮分文普通按钮（Button）与图片按钮（ImageButton）。
 
Button与ImageButton的共有特性：
**都可以作为一个按钮产生点击事件**

Button与ImageButton的不同点：

* ImageButton有src属性（图片内容），Button没有
* 同样Button有text属性，ImageButton没有

Button使用：通常text里面的文字内容放到strings.xml文件中，如下所示：

```
<Button
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/button"
        android:text="@string/button_name" />
```
```
<resources>
    <string name="button_name">按钮</string>
</resources>
```
ImageButton使用：图片存放在res文件夹下的drawable文件夹下（你也可以自己建文件夹）

```
<ImageButton
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/imageButton"
        android:src="@drawable/ic_launcher"/>
        
```

>src设置的是内容，background设置的是背景，如果将图片设置成背景，为了填满整个控件会变形，但是着两个属性可以同时存在

###修改Button的样式

通常我们使用的都是Android默认的Button样式，可能无法满足我们在开发中的需求，下面就来介绍可以修改Button样式的方法。

**更改按钮的点击颜色**

首先在res文件下的drawable文件夹下建立一个xml文件，文件内容如下：

```
<shape xmlns:android="http://schemas.android.com/apk/res/android">

    <corners android:radius="5dp"/>
    <solid android:color="@color/yellow"/>
</shape>
```
其中`<corners android:radius="5dp"/>`设置的是按钮的圆角程度

` <solid android:color="@color/yellow"/>`设置的是按钮的颜色

>在Eclipse中直接可以写出`@color/yellow`，但是在Android Studio中，这样写可能会报错，需要在res文件下的values文件下的colors.xml中设置，如下：

```
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="colorPrimary">#3F51B5</color>
    <color name="colorPrimaryDark">#303F9F</color>
    <color name="colorAccent">#FF4081</color>
    <color name="gray">#BBBBBB</color>
    <color name="yellow">#FFF000</color>
</resources>
```
接下来就是再在res文件下的drawable文件夹下建立一个xml文件，文件内容如下：

```
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:drawable="@drawable/gray_bg" android:state_pressed="true"/>
    <item android:drawable="@drawable/yellow_bg"/>
</selector>
```
>其中`<item android:drawable="@drawable/yellow_bg"/>
`是显示的默认情况下是黄色
` <item android:drawable="@drawable/gray_bg" android:state_pressed="true"/>`显示的按钮在按下的情况下显示灰色

最后在activity.xml文件中写上：

```
<Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/button"
        android:background="@drawable/gray_selector"
        android:text="@string/button_name"
        />
```
更改按钮的点击颜色就完成了，颜色可以按照需求和喜好来更换

下面的一些属性可以根据具体需求来进行添加

**`<item/>`表示一个动作或一个状态下的效果(下面属性都是boolean型)：** 

1. android:state_pressed `=true`表示按下状态使用（例如按钮按下）；`=false`表示非按下状态使用。 
2. android:state_focused `=true`表示聚焦状态使用（例如使用滚动球/d-pad聚焦button）；`=false`表示非聚焦状态使用。 
3. android:state_selected `=true`表示选中状态使用（例如tab打开）；`=false`表示非选中状态使用。 
4. android:state_checkable `=true`表示可勾选状态时使用；`=false`表示非可勾选状态使用。（只对能切换可勾选—非可勾选的构件有用。） 
5. android:state_checked `=true`表示勾选状态使用；`=false`表示非勾选状态使用。 
6. android:state_enabled`=true`表示可用状态使用（能接收触摸/点击事件）；`=false`表示不可用状态使用。 
7. android:window_focused `=true`表示应用程序窗口有焦点时使用（应用程序在前台）；`=false`表示无焦点时使用（例如notification栏拉下或对话框显示）。


**shape的属性：**

1. solid：指的是填充  
>android:color指定填充的颜色 

2. gradient：指的是渐变
>android:startColor和android:endColor分别为起始和结束颜色
#
android:angle是渐变角度，必须为45的整数倍。当angle=0时，渐变色是从左向右。
#
然后逆时针方向转，当angle=90时为从下往上。
#
另外渐变默认的模式为
#
android:type=”linear”，即线性渐变，可以指定渐变为径向渐变， 
#
android:type=”radial”，径向渐变需要指定半径
#
android:gradientRadius=”50”，也可一指定二者的综合，扫描渐变 android: type=”sweep” 

3. stroke： 指的是描边 
>android:width=”5dp” 描边的宽度，
android:color 描边的颜色。 
#
我们还可以把描边弄成虚线的形式，设置方式为： 
#
android:dashWidth=”10dp” android:dashGap=”3dp” 
#
其中android:dashWidth表示横线的宽度，android:dashGap表示之间隔开的距离。 

4. corners： 设置圆角 
>android:radius为角的弧度，值越大角越圆。 

**我们还可以把四个角设定成不同的角度，方法为：**

```
android:topRightRadius=”20dp” 右上角

android:bottomLeftRadius=”20dp” 右下角

android:topLeftRadius=”10dp” 左上角

android:bottomRightRadius=”10dp” 左下角 
```
>这里有个地方需要注意，bottomLeftRadius是右下角，而不是左下角 

关于button的简单复习就到这里了