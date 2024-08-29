---
title: "PA0学习记录"
subtitle: ""
description: ""
date: 2024-08-22T15:24:42+08:00
lastmod: 2024-08-22T15:24:42+08:00
draft: false

tags: ["一生一芯", "NJU PA"]
categories: []
series: ["一生一芯"]
series_weight: 2
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
<br>
{{<admonition>}}
本文是在一个月之后的复盘，所以很多细节都已缺失或不准确，以及每个人的配置不同，最终的结果也是不同的，请根据实际情况。
{{</admonition>}}

<!--more-->

## 发行版使用体验及总结

其实本来应该在4月20日考完专升本的考试之后就开始了的，但是折腾Linux环境就花了很久的时间，把大部分常见的发行版都折腾了一遍。具体有Debian，Ubuntu，Fedora，Arch，NixOS，Void Linux，openSUSE Tumbleweed，Gentoo Linux，Linux Mint……
<br>

##### 以下是具体发行版的折腾经历
> Debian

其实我第一个尝试的就是Debian，在高中的时候，仅仅只是为了装酷，虽然没有朋友去炫耀，但是装逼给自己看也不是不行，谁说不能自己一遍演戏一遍观赏的。

回归正题，这次当然装回了Debian，但是我又不想用Stable版本那陈旧的软件包，毕竟距离12发布也过去一年了，很多又开始落后了，Testing版本软件源并不是很全，所以用Unstable，结果在使用的过程中在安装一个doc时总是会冲突，后来用apptitude解决了（我不是很理解为什么不升级版本呢），当然其实是治标不治本的那种，就是放任不管（虽然我很好奇那为什么apt的时候不能直接忽略掉呢？），重新看了一遍文档，发现了一个问题，如果是从Stable切换到Unstable的话是要先切换到Testing，然后再切换到Unstable，因为Sid只能从Testing升级，很显然我犯了这个严重的错误，以下是相关的原文
<br>
{{<admonition abstract "Debian中文文档片段" false>}}

我该如何安装 Sid？

正规的答案是：Debian 从不发布 unstable。

你只能从 testing 升级至它。你可以以编辑 /etc/apt/sources.list 的方式更改你的软件源，从 testing 变为 unstable。（如果你安装的是稳定版，你应该先升级为 testing 再升级为 unstable。）

{{</admonition>}}
<br>
当然其实英文的文档表示是可以这么做的，但是我的确出了问题，后来重新安装Debian12，然后切换到Testing，最后Unstable，后面的流程一致。所以很迷。
<br>
{{< admonition abstract "Debian英文文档原文" false >}}

## Installation



There are no "unstable" full CD or DVD images. Due to the fact that the packages in "unstable" change so quickly, it is more appropriate for people to download and install "unstable" using a normal Debian FTP mirror.

If you are aware of the risks, choose one of the following ways to get set up on Sid:

- Use the current "[stable](https://wiki.debian.org/DebianStable)" installer to install a minimal stable system (**recommended**).

    - Change your [apt sources](https://wiki.debian.org/SourcesList) to point to "unstable".
    - Run `apt update` and `apt full-upgrade`.

- Use the current "[testing](https://wiki.debian.org/DebianTesting)" installer to install a minimal (next) stable system.

    - Change your [apt sources](https://wiki.debian.org/SourcesList) to point to "unstable".
    - Run `apt update` and `apt full-upgrade`.

- Use the Unstable "mini.iso" image.

    

    - Download the "mini.iso" for your CPU architecture located here: https://d-i.debian.org/daily-images/ under */daily/netboot/
    - During the installation choose "Advanced options" -> "Expert install".
    - In the step "Choose a mirror of the Debian archive" choose version "sid - unstable"

If you are already using a stable system use the method described above for upgrading to unstable changing your [apt sources](https://wiki.debian.org/SourcesList) from "stable" (or the codename for the current stable) to "unstable".

{{< /admonition >}}

<br>
还有就是经常被吐槽的一点就是Debian在启用了root用户后就不会把普通用户加入到sudo组，而且似乎不是常见的配置方式，至少我把用于加入了wheel组，但是并没能解决问题。用了网上奇奇怪怪的各种配置方式倒是成功了，但是说实话自己都没能搞清楚，所以不是很敢用。其他一切完美，Debian支持的那几个桌面环境打磨的很完美了。但是最后还是放弃了，放弃的理由会放在最后的，基本上除了现在在使用的Arch Linux以外理由都是一致的，当然Ubuntu不是。
<br>

> Ubuntu

对于很多人来说这是他们的第一个发行版，对我来讲是第三个？或者第四个？记不清楚了。

说实话我在Ubuntu上遇到各种各样的奇怪的、奇葩的问题，比如22.04及之前的版本，即使自定义分区了，但是它还是T！M！D！要把启动信息写到Windows所在的那个分区里去。关键问题是我T！M！D！是两块独立的硬盘啊啊啊啊！！！！有病吧。

而且在Windows上还没有那么容易删除掉，只能用一些取巧的办法，到时候有时间记录一下。

只能手动把另一块硬盘移除掉。不过从23.10之后就没有这个问题了，但是新的问题又tmd来了，24.04在不使用 `nomodeset` 的情况下竟然进不去图形界面，直接就是黑屏，无语了都……明明23.10和之前的都没有这个问题过，nm牛批。

当然这也~不是什么重要的问题，重要的问题是在独显模式下，tmd连个欢迎页面都直接报错，然后放着什么都tmd不动又出现了三个报错，而且看上去内容都不一致？？？还有就是好几个应用程序tm打不开，一开始还有报错，后面直接什么都没有，点一下，然后转几圈就没了。嗯，没了。

屮！！！换了驱动也不行，Nouveau、NVIDIA Open都不行，降级版本也不行，换到默认的X11就没问题了。后来发现混合模式也可以，推测应该是调用的是核显，所以无问题。

说实话非常奇葩的一个发行版，所有用过的都没有这么奇葩的问题过。

屮！芔！艹！草！操！！！！！！！！！！！！！！！！！！
<br>

> Arch

我第二个用的发行版就是Arch了，我不是很清楚为什么网上一堆都说是什么难以安装的发行版，还有一堆标了“残酷难度”的视频，按照wiki的来，然后去查一些相关的文章就很简单啊。而且使用也非常的简单，软件基本都是原生的，没有各种魔改、定制。我是挺喜欢KISS原则的。

唯一的一个问题就是Arch并不官方支持，包管理器也不支持多版本的解决问题。

其他就没啥了，近乎完美的一个发行版。

对了，补一个，如果是独显模式是无法直接进入Arch Live的，需要在启动参数中添加 `nomodeset`，怎么添加那就是 `RTFW` 的内容了。

<br>

> Gentoo

呃，最后应该算没成功来着，具体忘了在哪里卡着的，应该是在前面安装的时候哪里出问题了，然后也没办法解决，所以只能弃坑了。

我还是挺喜欢Gentoo的设计哲学的。

Gentoo是少有的几个对多版本管理很不错的发行版，想APT的update-alternative并不是很好，反正用不明白。

我觉我应该还会再次尝试的。

难过

<br>

> openSUSE Tumbleweed

仓库中的软件挺多的，有些发行版只有openSUSE Tumbleweed和Arch才会收录，连Gentoo都只有GURU Overlay才会有，不过考虑到Gentoo是半滚动的发行版，而且滚动的模型据说也和常见的不一致，所以也还能理解。

<br>

> Void Linux

是一个不使用systemd的发行版。

我对systemd无所谓，只不过某些软件或桌面环境对systemd强绑定的就很恶心了，例如GNOME。

只不过由于某个原因最后还是放弃，而且在国内很小众，国内的很多软件也没有现成的软件包。

<br>

> NixOS

设计哲学也是挺喜欢的（突然发现就是个渣男，这也喜欢，那也喜欢的），可复现，声明式，函数式，直接写文件来安装软件，当然是新的Nix Flake和Nix Command，原来的那个其实并不能很好的复现，而且如果要保证可复现的话就不能通过 `nix-env -iA` 来安装，但是尽然还有很多的软件的README或Installation还是使用该方法去指导安装的，可能对他们来讲还是这种常见的包管理器的安装方式更简单，也更好维护吧。

最后是卡在了安装 Home Manager 那里，而且很多的配置也没有搞懂，有些不应该使用软件原生的配置方式，应该使用NixOS的配置方式去配置。

最后还是弃坑了，后面应该还是会在NixOS和Gentoo中选一个去使用的。

<br>

> Fedora

Fedora其实基本就是先有的软件或驱动等的试验场，例如Wayland，PipeWire等都是先在Fedora上实验、推广的。

但是我在使用Neovim的时候竟然有报错，不知道是什么原因，一堆系统路径的lua文件报错，虽然不影响使用，但是还是有点膈应，所以也弃坑了。

不过还是记录几个有意思的东西：

1.在Fedora上安装软件的话回车键默认是no，不是yes。如果要使回车键是默认yes的话就需要修改dnf.conf，在上面添加一个 `defaulty=True`。

<br>

> Linux Mint

最新的虽然有Wayland了，但是进不去。

遂，弃之。

<br>

##### 发行版体验总结

主流的基本上都试了一遍。

Debian、openSUSE、Void Linux还有其他的发行版都遇到过同样的问题（不过其他的几个不是因为这个问题放弃的），每次明明安装完成了，两块硬盘最后也是独立的，但是每一次启动过Windows之后Linux的启动选项就从BIOS中消失了，用rEFInd工具也是一样的结果。最后的最后发现，原来是莫名其妙的把BIOS中的设定模式打开了，后来关闭之后及没问题了。

Ubuntu是因为这个发行版真的一言难尽。

Linux Mint是因为进不去Wayland，也没有解决办法。

Fedora是因为Neovim的问题。

NixOS是因为Home Manager以及使用不熟练，所以暂时弃坑了。

Gentoo应该是在安装的过程中某个参数或配置没有搞好，最后没有能力解决，所暂时弃坑了。

最后还是回到了Arch Linux的怀抱，因为简单，简洁。

<br>

## PA0总结
嗯，其实没什么好总结的吧，一切都挺简单的，都是很基础的内容。

需要注意的一些就是Arch对软件包的命名方式并不一样，例如在Debian系上的 `libsdl2` 在Arch上应该是 `sdl2`。还有一点，Arch的打包策略也不一样，例如GCC，在arch上只有一个gcc的软件包，实质上名为GCC（GNU Compiler Collection），而不是把gcc和g++分开打包，Arch一般不怎么拆包，所以看上去软件包的数量要少上许多。

在进行 `Compiling and Running NEMU` 内容时的问题在Arch上并没有遇到，似乎已经包括在了软件包组中，具体是哪一个不清楚，大概就是`base` 或 `base-devel` 吧。不过这个也不算什么大问题，只是前面 `Installing tools for PAs` 这一节时有部分工具没有安装而已。

报错信息很明显了，就是没有做一个颜色的区分才是最蛋疼的，可以考虑使用 `nala`，一个 `APT` 的前端（嗯，一个前端工具的前端）。

PA0提供的 `.vimrc` 倒是和我自己慢慢的配置差不多，不过我基本不用 `Vim`，还是 `Neovim` 更好一些，也不存在什么不兼容的，毕竟 `Neovim` 的教程直接丢了一个 `Vim` 的使用文档，除了 `lua` 的内容，以及例如 `NVIM_APPNAME` 这种独有的功能，对了，`NVIM_APPNAME` 的确是个不错的功能，到时候可以另外写一篇文章。

其他部分按照讲义的要求来走基本上不会出现什么问题。

配置多个ssh-key倒是会遇见一些奇奇怪怪的问题，主要是和GitHub有关，在学习记录上有说明，另外在obsidian的 `疑难问题` 中也有说明，看情况也会另外开一个文章。