---
title: "搭建Verilator仿真环境"
subtitle: ""
description: ""
date: 2024-08-23T15:29:04+08:00
lastmod: 2024-08-23T15:29:04+08:00
draft: false

tags: ["一生一芯", "Verilator"]
categories: []
series: ["一生一芯"]
series_weight: 4
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

## 首先安装 Verilator

> 首先安装 Verilator

<!--more-->

由于需要使用统一的Verilator的版本，这里现在是 Verilator v5.008。

<br>

之前在Debian，Ubuntu上都已经尝试过源码编译安装指定的版本，不过对于4.X的版本都有些问题，而且越早的问题就越多，最早的那几个就直接无法编译通过，有些版本 make test 会报错。其实也不是什么大问题，只要自己解决一下版本的问题的就行了，把兼容的依赖/库的版本放到FHS指定的路径下，然后在编译的时候指定一下使用哪些的依赖，反正我是如此解决的。不过5.X的版本肯定没有问题，所以其实不搭嘎。

<br>

但是新的问题又来了，如果是第一种，也就是官方推荐的 `Run-in-Place from VERILATOR_ROOT` ，在当前的Git路径下直接就地运行Verilator，不执行 make install 命令，不过后来遇到一个问题，那就是会提示找不到Perl（呃，应该是这个，毕竟当初是在Debian上做实验的，都是好几个月前了。大概……5月或6月？这都8月底了，23号了欸）。

其次是第二种的 `安装到指定前缀`，这个倒是没有这个问题了，但是我没吃透，所以就放弃了（搞得好像前面的我搞懂了一样）。

第三种全局安装，嗯，有一点点的洁癖和强迫症，无法接受（其实我还是喜欢第一种的方式）。

<br>

反正后来用的是Arch，当然在4.X的版本如果是手动编译安装的话，这些问题一个都逃不了，Debian这种老古董的都有问题欸，Arch上的肯定就更加不兼容了，好了伐。

当然的裆燃，downgrade 可以解决这个问题，在 Arch 的 Archive 上的软件包就不存在这个问题，可以正常使用。不过还是那句话，使用的是5.X的版本，我在虚拟机里就已经实验过了，同样也是没有问题的。唯一的缺点就是不支持或无法处理多版本的问题（emmm，其实这句话是放屁，Arch官方是完全能够解决这个问题的，只是他们不想做，或者不想实现而已。因为光一个 Electron，我的电脑上就TMD有Electron，Electron31，Electron30，Electron29）。

## **示例**
#### 双控开关
好吧，其实到现在为止（8.23），我还是没法理解 Verilog 的代码，以及下面的伪代码。不过多少还是能理解一些。

下面cpp的伪代码缺了一些东西。不过并不是很重要，有多个解决方式，可以丢到自定义函数或main函数中，都可以，另一个缺失的就是前面 `“复习”C语言` 提到的：

{{<admonition>}}

 还需要掌握一些简单的C++基础

verilator会编译出C++文件, 但你并不需要了解复杂的C++语法, 你只需要了解一些类(class)的基本使用方法就可以了. 单从这一点来看, 网上的很多资料都可以满足你的需求.

{{</admonition>}}

> 不过现在还是不懂，这个对应的cpp代码应该如何去写，大概要到后面去解锁了。

<br>

#### 打印并查看波形

没什么好写的，直接跳过。

<br>

#### 编写Makefile

前面抽空去看了一点Makefile的教程，但是还是不懂，这里的编写规则sim就完全是一脸懵。

该去学习 数字电路相关的内容了。

