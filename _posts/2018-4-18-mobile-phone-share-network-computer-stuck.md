---
layout: post
title:  "win10 手机usb共享网络,电脑卡死问题"
categories: Windows
tags:  Windows Win10 Network Android
author: hjxfire
---

* content
{:toc}
有时在Win10下使用手机usb共享网络时,会遇到电脑突然卡死的情况,以下是一种解决办法.
```
    1. 右击此电脑->管理->系统工具->设备管理器->网络适配器.
    2. 选择手机usb共享的那个网卡,一般是名字里有NDIS的那个.
    3. 然后右击->更新驱动程序->浏览我的计算机以查找驱动程序软件->让我从计算机上的可用驱动程序列表中选取.
    4. 接着取消勾选"显示兼容设备",在左边列表找到Microsoft,然后将右边列表拉到底,选择“远程NDIS兼容设备”这个，之后确定即可.
```
<hr style="background-color: rgb(25, 172, 230);height: 1px;">
因为是我好久以前遇到的问题,现在暂时没有贴图,以后有机会补上吧
