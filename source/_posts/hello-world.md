---
title: MarkDown语法详解
cover: 'https://file.pigax.cn/img/article/e150d263506oikG_compress78.jpg'
abbrlink: 4a17b156
categories: 爱学习
tags: [语法,MarkDown]
date: 2022/08/24/ 00:00:00
updated: 2022/08/24/ 00:00:00
description: MarkDown语法详解
keywords: 花语阁-MarkDown语法详解
---

# 前言

## 什么是MarkDown?

Markdown 是一种轻量级标记语言，它允许人们使用易读易写的纯文本格式编写文档。
Markdown 语言在 2004 由约翰·格鲁伯（英语：John Gruber）创建。
![约翰·格鲁伯](https://img0.baidu.com/it/u=3249522883,3793467588&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500)
Markdown 编写的文档可以导出 HTML 、Word、图像、PDF、Epub 等多种格式的文档。
Markdown 编写的文档后缀为 .md, .markdown。
由于Markdown的轻量化、易读易写特性，并且对于图片，图表、数学式都有支持，当前许多网站都广泛使用 Markdown 来撰写帮助文档或是用于论坛上发表消息。例如：GitHub、reddit、Diaspora、Stack Exchange、OpenStreetMap 、SourceForge等。甚至Markdown能被使用来撰写电子书。因此,很多博客把它当作语法来写,比如WordPress,Hexo,或者是Typecho.
常见的编辑器有[Typora](https://typora.io/)还有萌萌哒编辑器[Yosoro](https://yosoro.coolecho.net/)
下面开始讲

# 语法:

> 注意
> 文章内所有名字纯属虚构,如有雷同,纯属巧合!

## 文字

MarkDown的文字直接书写，与正常无区别
书写

{% tabs test2,2 %}
<!-- tab MD语法 -->
```MarkDown
直接书写即可
```
<!-- endtab -->

<!-- tab 样式预览 -->
我是刘老师.
<!-- endtab -->

<!-- tab 示例源码 -->
```MarkDown
我是刘老师.
```
<!-- endtab -->
{% endtabs %}

分隔符标题：

{% tabs test2,2 %}
<!-- tab MD语法 -->
```MarkDown
以-和=分隔成一级和二级标题:
```
<!-- endtab -->

<!-- tab 样式预览 -->
我是一级刘老师
---
我是二级刘老师
===
<!-- endtab -->

<!-- tab 示例源码 -->
```MarkDown
我是一级刘老师
---
我是二级刘老师
===
```
<!-- endtab -->
{% endtabs %}

> 注意:
> 无论是-还是=,只要三个及以上即可!

## 字符标题:

{% tabs test2,2 %}
<!-- tab MD语法 -->
```MarkDown
# 标题
## 标题
### 标题
#### 标题
##### 标题
###### 标题
```
<!-- endtab -->

<!-- tab 样式预览 -->
# 我是一级刘老师
## 我是二级刘老师
### 我是三级刘老师
#### 我是四级刘老师
##### 我是五级刘老师
###### 我是六级刘老师
<!-- endtab -->

<!-- tab 示例源码 -->
```MarkDown
# 我是一级刘老师
## 我是二级刘老师
### 我是三级刘老师
#### 我是四级刘老师
##### 我是五级刘老师
###### 我是六级刘老师
```
<!-- endtab -->
{% endtabs %}

> 注意
> 以#来做标题不得超过6个！

## 段落:

MarkDown的段落直接换行，与正常无区别.

## 字体:

MarkDown可用字体如下:

{% tabs test2,2 %}
<!-- tab MD语法 -->
```MarkDown
*文字*
_文字_
**文字**
__文字__
***文字***
___文字___
```
<!-- endtab -->

<!-- tab 样式预览 -->
*我是斜着的刘老师*
_我也是斜着的刘老师_
**我是粗粗的刘老师**
__我也是粗粗的刘老师__
***我是又粗又斜的刘老师***
___我也是又粗又斜的刘老师___
<!-- endtab -->

<!-- tab 示例源码 -->
```MarkDown
*我是斜着的刘老师*
_我也是斜着的刘老师_
**我是粗粗的刘老师**
__我也是粗粗的刘老师__
***我是又粗又斜的刘老师***
___我也是又粗又斜的刘老师___
```
<!-- endtab -->
{% endtabs %}

## 删除线:

{% tabs test2,2 %}
<!-- tab MD语法 -->
```MarkDown
用~~把要删除的文字包起来
```
<!-- endtab -->

<!-- tab 样式预览 -->
刘老师:今天试卷加~~三张~~ 四张!
<!-- endtab -->

<!-- tab 示例源码 -->
```MarkDown
刘老师:今天试卷加~~三张~~ 四张!
```
<!-- endtab -->
{% endtabs %}

## 引用(有时可做警告):

{% tabs test2,2 %}
<!-- tab MD语法 -->
```MarkDown
> 要引用文字

//还可以多级引用
> 要引用文字
>> 要引用文字
>>> 要引用文字
>>>> 要引用文字
>>>>> 要引用文字
>>>>>> 要引用文字
>>>>>>> 要引用文字
>>>>>>>> 要引用文字
>>>>>>>>> 要引用文字
```
<!-- endtab -->

<!-- tab 样式预览 -->
> 我是被引用的刘老师.
>> 我是被引用的刘老师.
>>> 我是被引用的刘老师.
>>>> 我是被引用的刘老师.
>>>>> 我是被引用的刘老师.
>>>>>> 我是被引用的刘老师.
>>>>>>> 我是被引用的刘老师.
>>>>>>>> 我是被引用的刘老师.
>>>>>>>>> 我是被引用的刘老师.
<!-- endtab -->

<!-- tab 示例源码 -->
```MarkDown
> 我是被引用的刘老师.
>> 我是被引用的刘老师.
>>> 我是被引用的刘老师.
>>>> 我是被引用的刘老师.
>>>>> 我是被引用的刘老师.
>>>>>> 我是被引用的刘老师.
>>>>>>> 我是被引用的刘老师.
>>>>>>>> 我是被引用的刘老师.
>>>>>>>>> 我是被引用的刘老师.
```
<!-- endtab -->
{% endtabs %}

## 代码:

### 单行代码:

{% tabs test2,2 %}
<!-- tab MD语法 -->
```MarkDown
用`包裹
```
<!-- endtab -->

<!-- tab 样式预览 -->
`我是被包裹的刘老师`
<!-- endtab -->

<!-- tab 示例源码 -->
```MarkDown
`我是被包裹的刘老师`
```
<!-- endtab -->
{% endtabs %}

### 代码块:

{% tabs test2,2 %}
<!-- tab MD语法 -->
```MarkDown
用```把代码块包裹起来
```
<!-- endtab -->

<!-- tab 样式预览 -->
```
我是被代码块包裹的刘老师
```
<!-- endtab -->

<!-- tab 示例源码 -->
````MarkDown
```
我是被代码块包裹的刘老师
```
````
<!-- endtab -->
{% endtabs %}

## 超链接:

{% tabs test2,2 %}
<!-- tab MD语法 -->
* 第一种
```MarkDown
[超链接标题](链接)
```
* 第二种
```MarkDown
<链接>
```
* 第三种
```MarkDown
[超链接标题][变量名]
[变量名]:链接
```
<!-- endtab -->

<!-- tab 样式预览 -->
第一种

[MarkDown语法详解](/posts/3eeb.html)

第二种

<https://www.baidu.com>

第三种

[MarkDown语法详解][1]

[1]: https://www.pigax.cn/posts/3eeb.html
<!-- endtab -->

<!-- tab 示例源码 -->
```MarkDown
[MarkDown语法详解](/posts/3eeb.html)

<https://www.baidu.com>

[MarkDown语法详解][1]

[1]: https://www.pigax.cn/posts/3eeb.html
```
<!-- endtab -->
{% endtabs %}

## 图片:

{% tabs test2,2 %}
<!-- tab MD语法 -->
```MarkDown
![图片标题](图片地址 "图片ALT")
```
<!-- endtab -->

<!-- tab 样式预览 -->
![刘老师](https://unpkg.pigax.cn/chenyfan-oss@1.0.0/pic/LLS.jpg "刘老师真容")
<!-- endtab -->

<!-- tab 示例源码 -->
```MarkDown
![刘老师](https://unpkg.pigax.cn/chenyfan-oss@1.0.0/pic/LLS.jpg "刘老师真容")
```
<!-- endtab -->
{% endtabs %}

## 排序:

### 无序排序:

{% tabs test2,2 %}
<!-- tab MD语法 -->
```MarkDown
使用+或-或*来做首标题
```
<!-- endtab -->

<!-- tab 样式预览 -->
+ 科学作业:无
+ 语文作业:翻倍
+ 数学作业:超级加倍
<!-- endtab -->

<!-- tab 示例源码 -->
```MarkDown
+ 科学作业:无
+ 语文作业:翻倍
+ 数学作业:超级加倍
```
<!-- endtab -->
{% endtabs %}

> 注意
> 无论是+或-或*,使用时与要列表的文字空一格空格!

### 有序列表:

{% tabs test2,2 %}
<!-- tab MD语法 -->
```MarkDown
使用数字+.+空格+文字代替,如:
```
<!-- endtab -->

<!-- tab 样式预览 -->
1. 写试卷
2. 写两张试卷
3. 写三张试卷
<!-- endtab -->

<!-- tab 示例源码 -->
```MarkDown
1. 写试卷
2. 写两张试卷
3. 写三张试卷
```
<!-- endtab -->
{% endtabs %}

> 警告
> 一定要加空格!

### 列表镶嵌:

{% tabs test2,2 %}
<!-- tab MD语法 -->
```MarkDown
+ 一级文字
    + 二级文字
1. 一级文字
    1. 二级文字
- 一级文字
    -二级文字
```

> 在第二列前加上Tab一个即可!
<!-- endtab -->

<!-- tab 样式预览 -->
+ 一级无序列表内容
	+ 二级无序列表内容
	+ 二级无序列表内容
	+ 二级无序列表内容

- 一级无序列表内容
	1. 二级有序列表内容
	2. 二级有序列表内容
	3. 二级有序列表内容

1. 一级有序列表内容
	+ 二级无序列表内容
	+ 二级无序列表内容
	+ 二级无序列表内容


1. 一级有序列表内容
	1. 二级有序列表内容
	2. 二级有序列表内容
	3. 二级有序列表内容
<!-- endtab -->

<!-- tab 示例源码 -->
```MarkDown
+ 一级无序列表内容
	+ 二级无序列表内容
	+ 二级无序列表内容
	+ 二级无序列表内容

- 一级无序列表内容
	1. 二级有序列表内容
	2. 二级有序列表内容
	3. 二级有序列表内容

1. 一级有序列表内容
	+ 二级无序列表内容
	+ 二级无序列表内容
	+ 二级无序列表内容


1. 一级有序列表内容
	1. 二级有序列表内容
	2. 二级有序列表内容
	3. 二级有序列表内容
```
<!-- endtab -->
{% endtabs %}

## 分隔符：

{% tabs test2,2 %}
<!-- tab MD语法 -->
```MarkDown
以- - -做分割线
```
<!-- endtab -->

<!-- tab 样式预览 -->
- - -
<!-- endtab -->

<!-- tab 示例源码 -->
```MarkDown
- - -
```
<!-- endtab -->
{% endtabs %}

## 列表:

{% tabs test2,2 %}
<!-- tab MD语法 -->
```MarkDown
|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |
```
<!-- endtab -->

<!-- tab 样式预览 -->
* 正常使用
|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |
* 特殊
|人物|技能一|技能二|技能三|大招|
|----|----|----|----|----|
|刘老师|讲一个段子|加一张试卷|/|考一场试|
|梁M法|抢体育课|<font color=yello>抢电脑课</font>|<font color=red>抢美术课</font>|<font color=green>连续考试</font>|
|刘老师老婆|[哭](https://baike.baidu.com/item/一哭二闹三上吊/838254)|[闹](https://baike.baidu.com/item/一哭二闹三上吊/838254)|[上吊](https://baike.baidu.com/item/一哭二闹三上吊/838254)|向刘老师发射一张离婚协议书.对其造成5000点物理伤害|
<!-- endtab -->

<!-- tab 示例源码 -->
* 正常使用
```MarkDown
|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |
```
* 特殊
```MarkDown
|人物|技能一|技能二|技能三|大招|
|----|----|----|----|----|
|刘老师|讲一个段子|加一张试卷|/|考一场试|
|梁M法|抢体育课|<font color=yello>抢电脑课</font>|<font color=red>抢美术课</font>|<font color=green>连续考试</font>|
|刘老师老婆|[哭](https://baike.baidu.com/item/一哭二闹三上吊/838254)|[闹](https://baike.baidu.com/item/一哭二闹三上吊/838254)|[上吊](https://baike.baidu.com/item/一哭二闹三上吊/838254)|向刘老师发射一张离婚协议书.对其造成5000点物理伤害|
```
<!-- endtab -->
{% endtabs %}

### 对齐:

{% tabs test2,2 %}
<!-- tab MD语法 -->
```MarkDown
使用+或-或*来做首标题
```
<!-- endtab -->

<!-- tab 样式预览 -->
| 左对齐 | 右对齐 | 居中对齐 |
| :-----| ----: | :----: |
| 单元格 | 单元格 | 单元格 |
| 单元格 | 单元格 | 单元格 |
<!-- endtab -->

<!-- tab 示例源码 -->
```MarkDown
| 左对齐 | 右对齐 | 居中对齐 |
| :-----| ----: | :----: |
| 单元格 | 单元格 | 单元格 |
| 单元格 | 单元格 | 单元格 |
```
<!-- endtab -->
{% endtabs %}

## 流程图:

Hexo用户可能要额外安装插件: `npm install --save hexo-filter-flowchart`

具体写法前往[官网](http://flowchart.js.org/)了解更多.

## 打出正常符号来:

{% tabs test2,2 %}
<!-- tab MD语法 -->
> 用\反斜杠来转义,转义表格如下:

| 你要打出的符号 | 你应该写出的符号 |
| --- | --- |
| \! | \\! |
| \` | \\` |
| \# | \\# |
| \- | \\- |
| \& | \\& |
| \* | \\* |
| \+ | \\+ |

<!-- endtab -->

<!-- tab 样式预览 -->
\!

\`

\#

\-

\&

\*

\+

<!-- endtab -->

<!-- tab 示例源码 -->
```MarkDown
\!

\`

\#

\-

\&

\*

\+

```
<!-- endtab -->
{% endtabs %}

## 公式:

### 单行公式:
用一个`$`来包裹单行代码(Hexo不支持)

### 多行公式：
用两个`$`来包裹单行代码(Hexo不支持)

## Todo:

{% tabs test2,2 %}
<!-- tab MD语法 -->
```MarkDown
[ ]代表为未完成的
[x] 代表完成的
```
<!-- endtab -->

<!-- tab 样式预览 -->
* [ ] 语文作业
* [x] 科学作业
<!-- endtab -->

<!-- tab 示例源码 -->
```MarkDown
* [ ] 语文作业
* [x] 科学作业
```
<!-- endtab -->
{% endtabs %}

> 注意
> 如果你显示不出来….
> 说明你踩坑里去了!
> 在每一个[ ]和[x]前要加上无序列表的符号!!
> 反正我是踩坑里去了!

## HTML标签：

{% tabs test2,2 %}
<!-- tab MD语法 -->
> Markdown本身就能与html互相转换

```MarkDown
[标题](链接)
```

转换

```HTML
<a href="链接">标题</a>
```
> 当然MarkDown可以和HTML一样使用html语法和css/js

```HTML
<标签 元素>文字<结束标签>
```

```HTML
<font color=颜色>文字</font>
```

```HTML
<p style="background:颜色">文字</p>
```

```HTML
<font size=大小>文字</font>
```

<!-- endtab -->

<!-- tab 样式预览 -->
# 链接
<a href="https://baidu.com">baidu</a>
# 按键符号
按<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Esc</kbd> 就可以调出任务管理器了！
# 上标
我是正常的刘老师<sup>我是上标刘老师</sup>
# 下标
我是正常的刘老师<sub>我是下标刘老师</sub>
# 改字体颜色
<font color=#F7FE2E>刘:我的心和我一样颜色</font>
# 改字体背景颜色
<p style="background:#F7FE2E">刘:我的心和背景一样颜色!</p>
# 改字体大小:
<font size=72>刘:我的\*和我一样大</font>

<!-- endtab -->

<!-- tab 示例源码 -->
```MarkDown
<a href="https://baidu.com">baidu</a>

按<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Esc</kbd> 就可以调出任务管理器了！

我是正常的刘老师<sup>我是上标刘老师</sup>

我是正常的刘老师<sub>我是下标刘老师</sub>

<font color=#F7FE2E>刘:我的心和我一样颜色</font>

<p style="background:#F7FE2E">刘:我的心和背景一样颜色!</p>

<font size=72>刘:我的\*和我一样大</font>

```
<!-- endtab -->
{% endtabs %}

不在 Markdown 涵盖范围之内的标签，都可以直接在文档里面用 HTML 撰写。
目前支持的 HTML 元素有：`&amp;lt;kbd&amp;gt; &amp;lt;b&amp;gt; &amp;lt;i&amp;gt; &amp;lt;em&amp;gt; &amp;lt;sup&amp;gt; &amp;lt;sub&amp;gt; &amp;lt;br&amp;gt;`等

> js/css
> 与正常使用无差异