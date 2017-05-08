---
layout: post
title: 获取RadioGroup与Radio、复选框CheckBox中的内容
tags:
- Android复习
categories: AndroidReview
description: 获取RadioGroup与Radio、复选框CheckBox中的内容
---
#获取RadioGroup与Radio、复选框CheckBox中的内容
Radio和CheckBox都是提供我们进行选择的控件，不同的是CheckBox是可以进行多选的，Radio只能进行单选，其实都很简单，本来是不想给自己做这个笔记的，但是想想做事应该有头有尾还是写了下面的小例子

###复选框CheckBox

```
<CheckBox
    android:id="@+id/checkbox"
    android:checked="true"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="排球"/>

    <CheckBox
        android:id="@+id/checkbox2"
        android:checked="false"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="篮球"/>
```
这里唯一需要注意的就是`checked`,设置为`true`是选中，`false`是没有选中

```
public class MainActivity extends Activity implements CompoundButton.OnCheckedChangeListener{
    private CheckBox checkBox;
    private CheckBox checkBox2;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        checkBox = (CheckBox) findViewById(R.id.checkbox);
        checkBox2 = (CheckBox) findViewById(R.id.checkbox2);
        checkBox.setOnCheckedChangeListener(this);
        checkBox2.setOnCheckedChangeListener(this);

    }

    @Override
    public void onCheckedChanged(CompoundButton buttonView, boolean isChecked) {
        if(checkBox.isChecked()){
            Toast.makeText(this,"选中的是:"+ checkBox.getText().toString(),Toast.LENGTH_SHORT).show();
        }
        if(checkBox2.isChecked()){
            Toast.makeText(this,"选中的是:"+ checkBox2.getText().toString(),Toast.LENGTH_SHORT).show();
        }
    }
}

```

###Radio与RadioGroup

```
<RadioGroup
    android:id="@+id/radioGroup"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:orientation="horizontal"
    >

    <RadioButton
        android:id="@+id/radio1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:checked="true"
        android:text="女"/>
    <RadioButton
        android:id="@+id/radio2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="男"
        />
</RadioGroup>
```

```
public class MainActivity extends Activity implements RadioGroup.OnCheckedChangeListener {
    private RadioGroup radioGroup;
    private RadioButton radio1, radio2;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        radioGroup = (RadioGroup) findViewById(R.id.radioGroup);
        radio1 = (RadioButton) findViewById(R.id.radio1);
        radio2 = (RadioButton) findViewById(R.id.radio2);
        radioGroup.setOnCheckedChangeListener(this);
    }


    @Override
    public void onCheckedChanged(RadioGroup group, int checkedId) {
        if (checkedId == radio1.getId()) {
            Toast.makeText(this, "你的性别是:" + radio1.getText().toString(), Toast.LENGTH_SHORT).show();
        }
        if (checkedId == radio2.getId()) {
            Toast.makeText(this, "你的性别是:" + radio2.getText().toString(), Toast.LENGTH_SHORT).show();
        }
    }
}
```

