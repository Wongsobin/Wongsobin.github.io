---
date: 2018-10-22 15:15
status: public
tags:
title: html语法之超链接标签详解
---

# HTML `<a> `标签
## 实例
**指向w3cshchool的超级链接**
```
<a href="http://www.w3school.com.cn">W3School</a>
```
## 定义和用法
`<a> `标签定义超链接，用于从一张页面链接到另一张页面。
`<a>` 元素最重要的属性是 href 属性，它指示链接的目标。
在所有浏览器中，链接的默认外观是：
未被访问的链接带有下划线而且是蓝色的
已被访问的链接带有下划线而且是紫色的
活动链接带有下划线而且是红色的
*提示：您可能已经注意到了，W3School 站点内的链接外观与默认的链接外观非常不同。您可以使用 CSS 伪类 向文本超链接添加复杂而多样的样式。*
## 术语解释:什么是超文本
**标记语言的真正威力在于其收集能力，它可以将收集来的文档组合成一个完整的信息库，并且可以将文档库与世界上的其他文档集合链接起来。**

**这样的话，读者不仅可以完全控制文档在屏幕上的显示，还可以通过超链接来控制浏览信息的顺序。这就是 HTML 和 XHTML 中的 “HT” - 超文本（hypertext），就是它将整个 Web 网络连接起来。**
## 超文本的基础知识
超文本的基本特征就是可以超链接文档；你可以指向其他位置，该位置可以在当前的文档中、局域网中的其他文档，也可以在因特网上的任何位置的文档中。这些文档组成了一个杂乱的信息网。目标文档通常与其来源有某些关联，并且丰富了来源；来源中的链接元素则将这种关系传递给浏览者。

超链接可以用于各种效果。超链接可以用在目录和主题列表中。浏览者可以在浏览器屏幕上单击鼠标或在键盘上按下按键，从而选择并自动跳转到文档中自己感兴趣的那个主题，或跳转到世界上某处完全不同的集合中的某个文档。

超链接还可以向浏览者指出有关文档中某个主题的更多信息。例如，“如果您想了解更详细的信息，请参阅某某页面。”。作者可以使用超链接来减少重复信息。例如，我们建议创作者在每个文档中都签署上自己的姓名。这样就可以使用一个将名字和另一个包含地址、电话号码等信息的单独文档链接起来的超链接，而不必在每个文档中都包含完整的联系信息。

超链接（hyper text），或者按照标准叫法称为锚（anchor），是使用 `<a>` 标签标记的，可以用两种方式表示。锚的一种类型是在文档中创建一个热点，当用户激活或选中（通常是使用鼠标）这个热点时，会导致浏览器进行链接。浏览器会自动加载并显示同一文档或其他文档中的某个部分，或触发某些与因特网服务相关的操作，例如发送电子邮件或下载特殊文件等。锚的另一种类型会在文档中创建一个标记，该标记可以被超链接引用。

还有一些与超链接相关联的鼠标相关事件。这些事件与 JavaScript 结合使用可以产生一些令人激动的效果。

## 注释
锚的这两种类型都使用同样的标签；也许这就是它们拥有同样的名称的原因。但是我们发现，如果将它们区分开，把提供热点和超链接地址的锚看作“链接”，而用于标记文档的目标部分的锚称为“锚”，那么您将更容易理解这两种类型的锚。
- - - - -
## 创建超链接
```
<html>
<body>
<p>
<a href="/index.html">本文本</a> 是一个指向本网站中的一个页面的链接。</p>
<p><a href="http://www.microsoft.com/">本文本</a> 是一个指向万维网上的页面的链接。</p>
</body>
</html>
```
显示结果
› 本文本 是一个指向本网站中的一个页面的链接。
› 本文本 是一个指向万维网上的页面的链接。

## 链接到同一个页面的不同位置
```
<html>
<body>
<p>
<a href="#C4">查看 Chapter 4。</a>
</p>
<h2>Chapter 1</h2>
<p>This chapter explains ba bla bla</p>
<h2>Chapter 2</h2>
<p>This chapter explains ba bla bla</p>
<h2>Chapter 3</h2>
<p>This chapter explains ba bla bla</p>
<h2><a name="C4">Chapter 4</a></h2>
<p>This chapter explains ba bla bla</p>
<h2>Chapter 5</h2>
<p>This chapter explains ba bla bla</p>
<h2>Chapter 6</h2>
<p>This chapter explains ba bla bla</p>
<h2>Chapter 7</h2>
<p>This chapter explains ba bla bla</p>
<h2>Chapter 8</h2>
<p>This chapter explains ba bla bla</p>
<h2>Chapter 9</h2>
<p>This chapter explains ba bla bla</p>
<h2>Chapter 10</h2>
<p>This chapter explains ba bla bla</p>
<h2>Chapter 11</h2>
<p>This chapter explains ba bla bla</p>
<h2>Chapter 12</h2>
<p>This chapter explains ba bla bla</p>
<h2>Chapter 13</h2>
<p>This chapter explains ba bla bla</p>
<h2>Chapter 14</h2>
<p>This chapter explains ba bla bla</p>
<h2>Chapter 15</h2>
<p>This chapter explains ba bla bla</p>
<h2>Chapter 16</h2>
<p>This chapter explains ba bla bla</p>
<h2>Chapter 17</h2>
<p>This chapter explains ba bla bla</p>
</body>
</html>

```
## 设置链接在新浏览器中打开
```
<html>
<body>
<a href="http://www.w3school.com.cn/" target="_blank">Visit W3School!</a>
<p>如果把链接的 target 属性设置为 "_blank"，该链接会在新窗口中打开。</p>
</body>
</html>
```
## 创建电子邮件（只带主题）
```
<html>
<body>
<p>
这是邮件链接：
<a href="mailto:someone@microsoft.com?subject=Hello%20again">发送邮件</a>
</p>
<p>
<b>注意：</b>应该使用 %20 来替换单词之间的空格，这样浏览器就可以正确地显示文本了。
</p>
</body>
</html>
```
## 创建电子邮件（带抄送、密送、邮件主题、邮件内容）
```
<html>
<body>
<p>
这是邮件链接：
<a href="mailto:someone@microsoft.com?subject=Hello%20again">发送邮件</a>
</p>
<p>
<b>注意：</b>应该使用 %20 来替换单词之间的空格，这样浏览器就可以正确地显示文本了。
</p>
</body>
</html>
```