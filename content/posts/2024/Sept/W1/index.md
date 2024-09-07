---
title: "2024.9-W1"
subtitle: ""
description: ""
date: 2024-09-02T14:27:12+08:00
lastmod: 2024-09-04T14:27:12+08:00
draft: true


tags: ["周记"]
categories: ["life"]
series: ["周记"]
series_weight: 2
hiddenFromHomePage: false
hiddenFromSearch: false

lightgallery: false

# 否开启表格排序
table:
  sort: false

toc:
  enable: true
  auto: false

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

2024.9.2-2024.9.9

{{</admonition>}}

<!--more-->

## 9月2日

### 学习记录

重新看了看数字电路基础部分，应该是要先数字电路再verilog的，只有一个英文的……

呃，有点看不下去，而且声音好小啊。

试着强行做那些习题，HDLBits和USTC Verilog OJ好像差不多，做着挺懵的，没有数点基础，也没有verilog基础，就看了一下基本的结构，唯一的基础就是之前让GPT拆解解读了一下 “双控开关” 的代码，稍微了解了一下，做到与门，这是真的做不出来了，前面的也是差不多试出来的。

第一题没问题。

第二题去看了一下相关的教程，大概这种情况是要指定的？反正是过了。

第三题，看样子应该是连线的，好像说是默认就是wire？但是不清楚为什么会有一个上升的波形啊，不应该是直上直下吗？看样子这里wire，assign都可以？到时候应该正规的去学一下。

第四题，呃，好像还是连线的，感觉和赋值差不多？

第五题，呃，反向？啊？不是很清楚`！`和`~`的区别，一个逻辑非，一个按位非，有啥区别吗？前面数电还没有进化到这个地步。

第六题，止步于此。



### 碎碎念

我裂开了

好菜

菜死了



---



## 9月3日

### 学习记录

无了



### 碎碎念

又去医院了，又配了点药，170支出了……都快能当饭吃了。

地铁上的时候看了看正式学院的学习记录，为啥那些零基础数电看上去也没学，看上去直接上手Verilog OJ和数电实验了。

好吧，感受到了参差，果然我是个垃圾。

不能再看下去了，再看我又要自闭了……



---



## 9月4日

C++应该把它当作是C语言的超集还是完全不同的语言呢。

Verilator里用C++写的不会就是激励文件吧。



### 碎碎念

马上要开学了，可以琢磨一下怎么用YubiKey加密Linux和用YubiKey登录Linux。

我觉得我大概率还要学个两个月左右，所以就先报名了，激励一下自个儿。



---



## 9月5日

### 学习记录

找了好多的数电相关的视频，打算快速过一遍，并不打算在这个阶段过于的深究，毕竟又用不到，学了也很快就忘了，边学边用的才学到还不错，Vim就是这么学来的，基础的会用了就行了，想要什么功能就去搜一搜有没有

逻辑上讲与非门是与门串联一个非门得到的，但是实际上内部逻辑是与门是由一个与非门串联一个非门来的，或门也是一样的，啧，玩的真野，爹是儿子生的，城里人真会玩。

两个非门串联得到的是不对电路逻辑产生影响的buffer，呃，那有什么用，不对逻辑产生影响，那实际电路嘞。

门电路的原理是基于一个器件--压控开关实现的，具体由三极管模拟实现。



### 碎碎念

我在想要不要把具体的学习记录移到另一个部分去，这里就写干了啥，学了啥。

感觉没有完全适合我的主题，多少都有点小问题（或者说是不适合我）。

plasmashell又不知道多少次crash了，每次都不知道是啥原因（那个贴出来的没啥用啊，反正我是没法根据那个找出来是什么原因），而且也不影响使用，好烦，没有好点的桌面环境了吗，能用的也就这几个，我也都试了个遍了。

要不，自个……

呃，算了，简直就是不自量力。

看了一圈相关的文章，大概以后还是使用Gentoo的好，在Gentoo上使用Nix就行了。其实nixos最吸引我的是那个nix-direnv，介绍说是“使用 cd 进入 nix 环境时，设置 direnv 来加载相关的环境”。

抽空学一点CSS，然后配置一下Waybar，用Hyprland去了，plasma以后就只用x11模式了，毕竟wemeet只能在x11下共享桌面，wayland那个虚拟摄像头太糊了，码率不行。

了解了一下运行时依赖和编译时依赖。

看到了一个OSTree（现在叫libostree），还是有点没有搞懂使用场景。



---



## 9月6日

### 碎碎念

其实Arch已经很完美了，唯一的问题就是不支持多版本，至少只能手动管理，只能手动安装在/opt或/usr/local/*中安装其他的版本，我尝试过这种方式，但是不知道会有什么后果或影响，而且当时也只是安装了这么一个版本，并没有从pacman中安装，所以没有测试过多版本的使用问题，在没有搞清楚之前是不打算使用这种方法的。

应该是和pacman本身有关系吧，pacman似乎不进行（或者是不能）对版本依赖性的解析，所以……不过这也算是优点吧，毕竟简单、高效、够用。

就是不知道Arch和Gentoo的repo哪个大一点（不过应该不好统计，毕竟有的不拆包的话看上去就会少很多），Gentoo有很多软件包都是存在于GURU中吧，例如Verilator就是。Arch的仓库足够大，基本上主流的软件包都有，没有的在AUR中也有，在非唯一性软件包数量中甚至高于Debian。

Gentoo的基于源码并不是很有吸引力，毕竟Arch实质上也有一个ABS替代。

有点乱……

打算把预学习的那几篇合并一下，感觉没有必要分出这么多篇。

原来git diff是和暂存区的文件做比较的，难怪好几次都没用，毕竟都已经commit了。

罢了，这一部分就删了，但是已提交的commit不知道怎么删除。

算了，暂时跳过吧，无所谓。



---



## 9月7日

### 碎碎念

timeshift还是不太靠谱，也有可能是Btrfs，不清楚具体是哪一个，在还原的时候又出问题了。

唯一可以记录的就是，重启可以解决90%的问题，在archiso中挂载之后arch-chroot可以解决98%的问题，重装可以解决99.9%的问题，剩下的就只能重新购买一台机器了。

还是写一下吧。

使用timeshift还原时，启动会出现报错，大概形如以下

~~~shell
[FAILED]Failed to mount /boot
[DEPEND]Dependency failed for Local File Systems.
You are in emergency mode. After logging in, typre "journalctl -xb" to view system logs, "systemctl reboot" to reboot, or "exit" to continue bootup.
Give root password for maintenance
(or press Control-D to continue):
~~~

这里最难受的一点在于这个界面无法接受输入，可能PS2接口的可以？不清楚为什么。其实应该是可以跳过启动引导的，手动解决，但是我不会……

一般这种情况就是内核版本不一致导致的无法挂载boot分区，然后就无法进去系统了，如果查看的话大概率还能发现“unknown filesystem type ‘vfat’ error”。

解决办法就是找一个archiso，然后依次挂载->chroot->pacman -Syu linux或者pacstrap -K /mnt linux（也可以把base base-devel linux linux-firmware linux-header都重新装一遍），最后exit后umount，reboot即可。
