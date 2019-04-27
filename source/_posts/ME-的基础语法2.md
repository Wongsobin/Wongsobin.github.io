---
title: ME 的基础语法
date: 2018-06-19 14:43:31
tags: [markeditor] ,[文字处理]
---

## 代码高亮语法
通过fenced code的方式(代码块的头尾被三个反引号包裹)，然后声明代码语言类型，即可实现代码高亮。不仅仅是最终的HTML预览会处理代码高亮，实时输入的过程中也是高亮的。
```python
s = 'hello world'
```

代码语言的类型后面跟上`:n`，则最终在渲染为HTML(预览)的时候，代码块会标示行数。
```python:n
s = 'hello world'
```

## 代码高亮示例
> MarkEditor支持超过300种代码类型的高亮，以下是一些示例:

```python
from settings import world
if world == 'mine':
   kept =  keep(world)
```

```ruby
sum = 1 + 2
a, b = 1, 2
1 > 2 ? true : false; puts 'Hi'
```

```swift
import Cocoa
let a = 4
var s = "Hello " + "World!"
```

```js
var express = require('express');
var app = express();
app.get('/', function(req, res){
  res.send('hello world');
});
app.listen(3000);
```