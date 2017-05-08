---
layout: post
title: Android控件复习之TextView、EditText与ImageView
tags:
- Android复习
categories: AndroidReview
description: Android的控件复习之TextView、EditText与ImageView
---

#Android控件复习之TextView、EditText与ImageView

首先来介绍一下TextView、EditText与ImageView

* **TextView**是显示文本框控件，不能进行文本编辑
* **EditText**是输入文本框，可以进行文本编辑
* **ImageView**是显示图片的一个控件

**TextView**的常用属性：

```
除了每个控件都有的属性：
android:id-------------------控件的id
android:layout_width---------控件的宽度
android:layout_height--------控件的高度

还有一下属性：
android:text-----------------文本内容
android:textSize-------------文本大小
android:textColor------------文本颜色
android:background-----------文本背景
```
>这里在设置文字大小的时候还需要注意一个小知识：
那就是字体大小的单位，有三种，分别是
#
`px`、`dp`（或`dip`）与`sp`
#
一般来讲我们不怎么使用`px`，因为它不能根据屏幕的分辨率开进行缩放，也就是你设置成多大，它就是多大
#
`sp`与`dp`（或`dip`）是可以根据屏幕的分辨率进行等比的缩放的
#
`dp`（或`dip`）是使用在控件与控件的间隔上
#
`sp`一般使用在文字大小上

**EditText**的常用属性：

除了有上面TextView的属性外，EditText还有以下常用属性：

```
android:hint-----------------输入提示文本（获得焦点后可自行消失）
android:inputType------------输入文本类型（可以设定输入的文本类型，如：数字，纯英文等）
```
>这里`android:layout_width`与`android:layout_heigh`都分别有三个属性值分别是：
#
wrap_content-------------包裹实际文本内容
#
match_parent-------------当前控件铺满父类容器（现在主要使用这个，是2.3API之后添加的一个属性值）
#
fill_parent--------------当前控件铺满父类容器（2.3API之前就有的属性值）

**ImageView**常用属性：

```
android:id-------------------控件的id
android:layout_width---------控件的宽度
android:layout_height--------控件的高度
android:src------------------设置ImageView的内容图像
android:background-----------设置ImageView的背景图片或者颜色
```
[ImageView.ScaleType设置图解](http://blog.csdn.net/larryl2003/article/details/6919513)