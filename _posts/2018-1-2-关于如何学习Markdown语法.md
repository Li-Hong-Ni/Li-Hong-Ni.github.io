---
layout: article
title:  "如何学习Markdown语法"
date:   2017-12-31 18:07:50 +0800
categories: posts rwd
image:
  teaser: markdown.png
  feature: markdown.png
---

## 关于如何掌握Markdown语法
### 宗旨  
Markdown 的目标是实现「易读易写」。可读性，无论如何，都是最重要的。一份使用 Markdown格式撰写的文件应该可以直接以纯文本发布，并且看起来不会像是由许多标签或是格式指令所构成。  
总之， Markdown 的语法全由一些符号所组成，这些符号经过精挑细选，其作用一目了然。  
### 兼容 HTML  
Markdown 语法的目标是：成为一种适用于网络的书写语言。不在 Markdown 涵盖范围之内的标签，都可以直接在文档里面用 HTML 撰写。不需要额外标注这是HTML或是Markdown；只要直接加标签就可以了。  
例子如下，在 Markdown 文件里加上一段 HTML 表格：  
```
这是一个普通段落。

<table>
    <tr>
        <td>Foo</td>
    </tr>
</table>

这是另一个普通段落。  
```  
请注意，在 HTML 区块标签间的 Markdown 格式语法将不会被处理。比如，你在 HTML 区块内使用 Markdown 样式的*强调*会没有效果。

HTML 的区段（行内）标签如  ``` <span>、<cite>、<del> ```  可以在 Markdown 的段落、列表或是标题里随意使用。依照个人习惯，甚至可以不用 Markdown 格式，而直接采用 HTML 标签来格式化。举例说明：如果比较喜欢 HTML 的 <a> 或 <img> 标签，可以直接使用这些标签，而不用 Markdown 提供的链接或是图像标签语法。

和处在 HTML 区块标签间不同，Markdown 语法在 HTML 区段标签间是有效的。  
### 区块元素  
##### 段落和换行  
###### 标题  
Markdown 支持两种标题的语法，类 Setext 和类 atx 形式。类 Setext 形式是用底线的形式，利用 =（最高阶标题）和 - （第二阶标题），例如：  
```
This is an H1
=============

This is an H2
-------------
```  
任何数量的 = 和 - 都可以有效果。类 Atx 形式则是在行首插入 1 到 6 个 # ，对应到标题 1 到 6 阶，例如：  
```
# 这是 H1

## 这是 H2

###### 这是 H6
```
###### 区块引用 Blockquotes  
Markdown 标记区块引用是使用类似 email 中用 > 的引用方式。  
```> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
> 
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.   
```  
引用的区块内也可以使用其他的 Markdown 语法，包括标题、列表、代码区块等：  
```> ## 这是一个标题。
> 
> 1.   这是第一行列表项。
> 2.   这是第二行列表项。
> 
> 给出一些例子代码：
> 
>     return shell_exec("echo $input | $markdown_script");  
```  
### 列表  
Markdown 支持有序列表和无序列表。

无序列表使用星号、加号或是减号作为列表标记： 
```  
*   Red
*   Green
*   Blue  
```  
等同于：  
```  
+   Red
+   Green
+   Blue    
 ```  
也等同于  
```  
也等同于  
```  
有序列表则使用数字接着一个英文句点：  
```  
1.  Bird
2.  McHale
3.  Parish  
```  
很重要的一点是，你在列表标记上使用的数字并不会影响输出的 HTML 结果，上面的列表所产生的 HTML 标记为：  
```  
<ol>
<li>Bird</li>
<li>McHale</li>
<li>Parish</li>
</ol>  
```  
### 代码区块  
和程序相关的写作或是标签语言原始码通常会有已经排版好的代码区块，通常这些区块我们并不希望它以一般段落文件的方式去排版，而是照原来的样子显示，Markdown 会用``` <pre> ```和 ```<code>``` 标签来把代码区块包起来。   
要在 Markdown 中建立代码区块很简单，只要简单地缩进 4 个空格或是 1 个制表符就可以，例如，下面的输入：  
```
这是一个普通段落：
这是一个代码区块。  
```  
Markdown 会转换成：  
```
<p>这是一个普通段落：</p>

<pre><code>这是一个代码区块。
</code></pre>
```  
### 分隔线  
你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线  
```  
* * *

***

*****

- - -

---------------------------------------  
```  
### 区段元素  
Markdown 支持两种形式的链接语法： 行内式和参考式两种形式。

不管是哪一种，链接文字都是用 [方括号] 来标记。

要建立一个行内式的链接，只要在方块括号后面紧接着圆括号并插入网址链接即可，如果你还想要加上链接的 title 文字，只要在网址后面，用双引号把 title 文字包起来即可，例如：  
```
This is [an example](http://example.com/ "Title") inline link.  

[This link](http://example.net/) has no title attribute.  
```
会产生:  
```  
<p>This is <a href="http://example.com/" title="Title">
an example</a> inline link.</p>

<p><a href="http://example.net/">This link</a> has no
title attribute.</p>  
```  
### 强调  
Markdown 使用星号（*）和底线（_）作为标记强调字词的符号，被 * 或 _ 包围的字词会被转成用 ```em>``` 标签包围，用两个 * 或 _ 包起来的话，则会被转成```<strong>```。  
### 图片

很明显地，要在纯文字应用中设计一个「自然」的语法来插入图片是有一定难度的。

Markdown 使用一种和链接很相似的语法来标记图片，同样也允许两种样式： 行内式和参考式。

行内式的图片语法看起来像是：   
```  
![Alt text](/path/to/img.jpg)

![Alt text](/path/to/img.jpg "Optional title")  
```



