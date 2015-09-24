---
layout: post
title: "Undefined symbols for architecture i386"
date: 2015-09-24 16:09:09 +0800
comments: true
categories: error
 
---
![](https://github.com/YanceyChan/YanceyChan.github.io/blob/source/source/images/20150702134813838.png?raw=true)


项目新添加了一个第三方framework，结果编译提示错误了。
检查了一下Link Binary With Libraries  发现是有添加这个库的，而且还有2个。。。

![](https://github.com/YanceyChan/YanceyChan.github.io/blob/source/source/images/20150702135032311.png?raw=true)

删除一个，再编译，失败，
删除两个，再重新添加，编译，继续失败

是不是因为这个库只能在真机情况下才能编译成功？？明天拿真机来试试看。

最后的最后。。。真的是因为XXX.framework  只能用真机编译啊。。。╮(╯▽╰)╭蛋疼。
