---
title: Hexo博客撰写之：MarkDown语法　（还有新歌推送<丹宁执着完整版>）
date: 2017-08-27 09:12:00
categories:
  - 其他
tags:
  - hexo
  - markdown
description: 介绍如何在hexo搭建的博客下用markdown写文章,以及一些markdown的基本语法．
---


# 新歌推送（丹宁执着完整版）
&emsp;&emsp;&ensp;消除联萌是JJ林俊杰精心筹划了近一年的全新“虚拟乐团”，这次是JJ首次以“师父”的身份亲自带领四名正式团员亮相。JJ还特别邀请获得包括“年度制作”及“最佳摇滚专辑”等多项格莱美殊荣的“混音之王”Chris Lord-Alge参与制作，强烈风格让这首歌有着让人一听着迷的魅力。据悉，《丹宁执着》的灵感就是来自那个“改变时尚世界的牛仔裤”的爱情故事。而JJ被这样的爱情所打动，有感而发的写下了这首歌。

<center>
<video width="320" height="220" src='http://tb-video.bdstatic.com/tieba-smallvideo/250_9e5fdc5aaa8282d45cfcbccd677d3f35.mp4' controls='controls' > 
您的浏览器不支持 video 标签。 
</video>
</center>

&emsp;&emsp;&ensp;【歌曲详情】

　　你可知道，你身上穿的那件牛仔裤，蕴含著爱情，还浇注了一分热忱和感动。

　　当布商 Levi Strauss 和裁缝师 Jacob Davis 得知一位女性客户提出，请他们缝製出一条耐用不怕磨损的裤子，给心爱的丈夫在砍伐木材时穿著不那麽容易破损，使他们製作加固牛仔裤的概念得到启发，进而改变世界的牛仔裤诞生了!

　　JJ林俊杰深深被这样纯粹的爱情打动，加上「丹宁」精神就是既结实又柔软，已有许多隽永的爱情篇章写不完，那就用这份对音乐的热忱与纯粹，以阳光般温暖的音符谱出这首听来热血沸腾的「消除联萌」首支单曲《丹宁执著》!

　　这次也因著JJ林俊杰一如既往对作品的坚持信念，希望将最棒的作品呈现给大家，特别请到了「神级混音大师」Chris Lord-Alge 为这首《丹宁执著》进行混音。Chris Lord-Alge 是美国知名混音师，如果你喜欢摇滚乐，那你一定十分熟悉他的声音!

　　Chris Lord-Alge 参与过的专辑获得许多葛莱美奖，他也拥有另外一个名字叫「Lord of the Mix(混音之王)」，因为他的风格强烈，会让人听过就难以忘怀的著迷。


---

# 前言
&emsp;&emsp;&ensp;装过linux和win双系统的同学都知道,装完从Lin转到Win后，Win的系统时间会变成了格林尼治时间（也就是本地时间-8H）.另外,装完Win后,启动引导变成了linux的grub,linux变成了默认启动项,那如果想把Win设为默认启动项呢,别急,下面轻松搞定.


# 时间同步设置
&emsp;&emsp;&ensp;废话不多说,一条命令搞定Lin和Win时间同步:
``` bash
$ timedatectl set-local-rtc 1
```
搞定,想看详细情况的话可以输入以下命令:
``` bash
$ timedatectl 
```
OK,这时候重启进入Win,你会发现Win的时间对了,哈哈哈.


# 默认启动项设置
&emsp;&emsp;&ensp;进入linux系统,执行以下操作,
``` bash
$ sudo gedit /etc/default/grub
```
这时候gedit会打开grub文件,将
```
GRUB_DEFAULT=0
```
改成Win的序号,启动顺序默认从0开始,同时还可以修改”GRUB_TIMEOUT=10“中的默认等待时间，比如改成5秒,改好之后,保存关闭.然后执行
``` bash
$ sudo update-grub
```
OK搞定,这时候重启进入grub菜单,你会发现默认启动项已经变成了Win^_^







