---
layout: post
title: Android Studio For Mac快捷键
tags:
- Android Studio快捷键
categories: IDE
description: Android Studio For Mac快捷键
---
这里有几个Max OS x 下Android studio 的快捷键

常用的AS中的操作 **(⌘:command, ⌃:ctrl, ⇧:shift, ⌥:alt/option, ⏎:enter/return )** 

- 保存，⌘s    

这个在AS中其实是自动保存的。即使关闭Tab页后，再次打开，⌘z还是可以撤销编辑的

- getter、setter、toString、constructor...       ⌘n


- 类层级：⌃h 
- 在当前project(一个project可以含多个moudle)中搜索class：⌘o
   
    再按一次⌘o(会发现，右上角的选项勾选了)，搜索结果可包含非project中的class，如external libraries中的android.jar里的class
    
    可以在搜索文本后跟:lineNumber   从而定位到某行
    
- 在当前project中搜索file(包含上面的class结果)：⌘⇧o
   
    再按一次⌘⇧o，搜索结果可包含非project中的flie，如external libraries中的res里的file
    可以在搜索文本后跟:lineNumber   从而定位到某行，如 输入文本：mainacti:20  这时就会定位到MainActivity的20行
- 在当前project中搜索属性(成员和静态，不论是否私有) ⌘⌥o  
     再按一次，搜索结果可包含非project中的class
- 如eclipse中的⌘1的action(即win-eclipse上的ctrl+1)：⌥⏎    quick fix
    即alter+enter (需要光标移动到分号之前，可以在代码内容里，当该代码行下标红时)
- 如eclipse中的⌘⇧2+L(自动声明变量) : ⌘⌥v
- 如eclipse中的⌘o(查看当前类成员):     ⌘F12， 显示内部成员
      ⌘i 显示/取消息匿名类
      ⌘f12 显示继承自父类、父接口的成员
- 选择能重写(override)或实现(implement)的方法 ：⌃o
- 如eclipse中的⌘⇧G，查找方法在哪被使用：⌥F7
- 定位到属性、方法、类等它们的声明：F4
- 查看父类的同名方法：⌘U
- 光标在调用接口方法的方法名中，查看接口方法实现类：⌘⌥B 或 ⌘⌥click
- Surround With: if、while、try-catch、synchronized 等等：⌘⌥T
- 重构面板：⌃T
- Extract Method 抽取成方法：⌘⌥M
- Extract Field 抽取为成员属性：⌘⌥F
- Extract Parameter 将内部变量抽取成方法的参数：⌘⌥P
- 去除无效引用： ^⌥O
- 整理代码且能去除无效引用：⌘⌥L
- open recent file 历史打开过的文件： ⌘E
- find usages 查找使用情况：⌘⌥⇧F7
- 查找与替换：⌘F，⌘R
     在查找后，使用⌘G 定位到下一个text
     find in path与replace in path：⌘⇧F，⌘⇧R
-  大小写转换：⌘⇧U
-  重命名：⇧F6
-  光标换行：⌘⇧⏎  
-  在当前行上添加一行，光标定位到行首：⌘⌥⏎  
-  复制整行：⌘D
-  删除整行：⌘delete
-  内容行上下移动，不会出方法体；或光标在方法体外且在方法行上时，移动整个方法：⇧⌘↑|↓ 
-  上下移动光标所在行：⌥⇧↑|↓ 
-  剪切，若无选中文本时会剪切整行：⌘X
-  查看doc/文档注释：F1
-  定位到未使用的声明 F2 
-  ⌘j ：快捷代码片段


```
      psf => public static final 
      ifn => if (a == null)
      inn=> if (a != null)
     fori=> for(int i = 0; i < .....)
     I(大写i)=> for(Object o : ) 
    ..... 其它 
    
```
- 最后是代码提示 ALT/