---
title: Markdow常用基础语法
date: 2019-07-27 15:13:34
tags: 
    - Markdow基础语法
categories: 随笔
comments: true
---


# 一、标题

# 这是一级标题
## 这是二级标题
### 这是三级标题
#### 这是四级标题
##### 这是五级标题
###### 这是六级标题

语法如下：
```
# 这是一级标题
## 这是二级标题
### 这是三级标题
#### 这是四级标题
##### 这是五级标题
###### 这是六级标题
```


# 二、字体

**这是加粗的文字**
*这是倾斜的文字*`
***这是斜体加粗的文字***
~~这是加删除线的文字~~

语法如下：
```
**这是加粗的文字**
*这是倾斜的文字*`
***这是斜体加粗的文字***
~~这是加删除线的文字~~
```


# 三、引用

>这是引用的内容
>>这是引用的内容
>>>>>>>>>>这是引用的内容

语法如下：
```
>这是引用的内容
>>这是引用的内容
>>>>>>>>>>这是引用的内容
```


# 四、分割线

---
----
***
*****

语法如下：
```
---
----
***
*****
```


# 五、图片

![图片](https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1563096787830&di=3b6724111b31f09ee19d16763bbd3a21&imgtype=0&src=http%3A%2F%2Ff.hiphotos.baidu.com%2Fimage%2Fpic%2Fitem%2Fa71ea8d3fd1f4134d244519d2b1f95cad0c85ee5.jpg)

语法如下：
```
![图片alt](图片地址 ''图片title'')

图片alt就是显示在图片下面的文字，相当于对图片内容的解释。
图片title是图片的标题，当鼠标移到图片上时显示的内容。title可加可不

![图片](https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1563096787830&di=3b6724111b31f09ee19d16763bbd3a21&imgtype=0&src=http%3A%2F%2Ff.hiphotos.baidu.com%2Fimage%2Fpic%2Fitem%2Fa71ea8d3fd1f4134d244519d2b1f95cad0c85ee5.jpg)
```

# 六、超链接

[简书](http://jianshu.com)
[百度](http://baidu.com)

语法如下：
```
[简书](http://jianshu.com)
[百度](http://baidu.com)
```

# 七、列表

- 列表内容
+ 列表内容
* 列表内容

注意：- + * 跟内容之间都要有一个空格

```
- 列表内容
+ 列表内容
* 列表内容

注意：- + * 跟内容之间都要有一个空格
```


1.列表内容
2.列表内容
3.列表内容

注意：序号跟内容之间要有空格

```
1.列表内容
2.列表内容
3.列表内容

注意：序号跟内容之间要有空格
```


# 八、表格

姓名|技能|排行
--|:--:|--:
刘备|哭|大哥
关羽|打|二哥
张飞|骂|三弟

语法如下：
```
表头|表头|表头
---|:--:|---:
内容|内容|内容
内容|内容|内容

第二行分割表头和内容。
- 有一个就行，为了对齐，多加了几个
文字默认居左
-两边加：表示文字居中
-右边加：表示文字居右
注：原生的语法两边都要用 | 包起来。此处省略
```

# 九、代码

代码之间分别用一个反引号包起来
`create database hero;`
语法如下：
```
`create database hero;`
```



# 十、扩展

给字体加颜色：
<font style="color:red">这是红色字体<font>>

代码如下：
```
<font style="color:red">这是红色字体<font>
```

换行：

这是红色<br/>字体

代码如下：
```
这是红色<br/>字体
```
