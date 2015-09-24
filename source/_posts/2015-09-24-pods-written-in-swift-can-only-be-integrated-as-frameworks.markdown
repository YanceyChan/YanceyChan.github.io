---
layout: post
title: "Pods written in Swift can only be integrated as frameworks"
date: 2015-09-24 16:53:46 +0800
comments: true
categories: error

---
[!] Pods written in Swift can only be integrated as frameworks; this feature is still in beta. Add `use_frameworks!` to your Podfile or target to opt into using it. The Swift Pods being used are: Box, ReactiveCocoa, and Result

用PODS 添加RAC的时候出现这样的问题提示

![这里写图片描述](https://github.com/YanceyChan/YanceyChan.github.io/blob/source/source/images/20150923140859601.png?raw=true)

可能是RAC 不支持swift导致
解决办法：在podfile里面添加 use_frameworks
![这里写图片描述](https://github.com/YanceyChan/YanceyChan.github.io/blob/source/source/images/20150923142933623.png?raw=true)
