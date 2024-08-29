---
title: "复（Xué）习（Xí）C语言"
subtitle: ""
description: ""
date: 2024-08-22T23:53:25+08:00
lastmod: 2024-08-23T23:53:25+08:00
draft: false

tags: ["C", "C语言", "一生一芯"]
categories: []
series: ["一生一芯"]
series_weight: 3
hiddenFromHomePage: false
hiddenFromSearch: false

lightgallery: false

# 否开启表格排序
table:
  sort: false

toc:
  enable: true

comment:
  utterances:
    enable: true
  waline:
    enable: false
  disqus:
    enable: false
---

TO BE DONE...

{{<admonition>}}
主要是记录C语言的一些笔记，外加预学习中对于LCTHW中那些习题的要求的解题思路
{{</admonition>}}

<!--more-->

<br>

## LCTHW 附加题解题思路

> ex1

略过

> ex2

略过

> ex3

略过

> ex4

略过

> ex5

略

> ex6

略

> ex7

略

> ex8

略

> ex9

略

> ex10

略

> e11

略

> ex12

略

> ex13

略

> ex14

略

> ex15

略

> ex16

略

> ex17

略

> ex18

略



<br>



## C语言笔记

> 指针

~~~C
int *p, q;
q = 10;
p = &q;
*p = 13;
~~~

声明了一个名为 p 的指针变量。

**`p = &q;` **：`&q` 代表的是 变量q 的地址，而 *p 代表的是 指针p 指向内存位置的值。

换个解释方式就是：q 是一个变量，在上面给它赋了一个值，为10。&是取址符，&q 代表的是获取变量q在内存中的地址，p是一个指向整数的指针。而p = &q; 是把q的地址指向了p（或者说是将q的地址（也就是&q）赋值给p），p就想是一个指向内存地址的标签，在这里就是p这个标签指向了q所在的内存空间。\*是指针解引用，*p就是指针解引用的操作，用来获取p指向的内存位置上的值。

{{<admonition warning>}}

以上是为了方便自己理解，有不少的逻辑漏洞。

请参考相关的 [C语言标准-草案版](https://zh.cppreference.com/w/c)

鉴于最终版的草案与正式标准几乎无差别，所以提供的链接是草案版的。

{{</admonition>}}
