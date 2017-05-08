---
title: 使用javascript最简单有效的定位当前日期是星期几的方法
date: 2017-04-13 16:12:31
tags: [js,日期]
categories: javascript
---
## 对于如何zz获取当前日期是星期几的做法，我想最常用的做法就是利用js的switch,case方法。
<!-- more -->
这里提供一个三行代码解决的方法（不要太激动哦！！！）
```
var num = new Date().getDay();
var str="日一二三四五六";
var day=str.charAt(num);
console.log("今天星期",day);

```
这个方法充分利用了字符串的charAt()方法，因为当num等于0的使用正好对位到了字符串str的第一个字符位置，这种方法简单且容易理解，推荐大家使用。
