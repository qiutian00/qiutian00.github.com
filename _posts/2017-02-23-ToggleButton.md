---
layout: post
title: Android控件复习之ToggleButton
tags:
- Android复习
categories: AndroidReview
description: Android的控件复习之ToggleButton
---
#Android复习之ToggleButton

**ToggleButton**有两种状态：

* 选中状态
* 未选中状态

并且要为不同的状态设置不同的显示文本

**ToggleButton**属性：

```
android:checked="true"
android:textoff="关"
android:texton="开"
```
####Demo

xml:

```
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <ToggleButton
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/toggleButton"
        android:checked="true"
        android:textOn="开"
        android:textOff="关"
        />
   <ImageView
       android:layout_width="match_parent"
       android:layout_height="match_parent"
       android:id="@+id/imageView"
       android:background="@drawable/on"/>

</LinearLayout>

```
```
public class MainActivity extends Activity implements CompoundButton.OnCheckedChangeListener {
    private ToggleButton toggleButton;
    private ImageView imageView;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        toggleButton = (ToggleButton) findViewById(R.id.toggleButton);
        imageView = (ImageView) findViewById(R.id.imageView);
        /*
            给当前的ToggleButton添加监听
        */

        toggleButton.setOnCheckedChangeListener(this);
    }

    @Override
    public void onCheckedChanged(CompoundButton buttonView, boolean isChecked) {
        /*
            当前ToggleButton被点击的时候当前的方法执行

         */
        imageView.setBackgroundResource(isChecked?R.drawable.on:R.drawable.off);

    }
}

```
>图片可以自己随意添加

