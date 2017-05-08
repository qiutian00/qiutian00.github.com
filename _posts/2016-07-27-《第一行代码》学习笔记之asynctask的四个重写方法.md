---
layout: post
title: 《第一行代码》学习笔记之AsyncTask的四个重写方法
tags:
- AsyncTask
categories: Android
description: 《第一行代码》学习笔记之AsyncTask的四个重写方法
---

## 《第一行代码》学习笔记之AsyncTask的四个重写方法

1. **onPreExecute（）:**

	这个方法在后台服务开始执行之前调用。用于进行一些界面上的初始化操作，比如显示一个进度条对话框等。

2. **doInBackground():**

	这个方法中的所有代码都会在子线程上运行，应该处理耗时操作，不可以进行UI操作，如需要更新UI元素，可以调用publishProgress()方法完成
3. **onProgressUpdate():**

	在后台服务中调用publishProgress()之后，该方法被很快调用，方法中携带的参数就是后台任务中传递过来的，这个方法可以对UI进行操作
4. **onPostExecute():**

	当后台任务执行完毕并通过return语句进行返回时，改方法被调用，并且可以利用返回的数据来进行一些UI操作，如提醒任务执行的结果，以及关闭掉进度条对话框等