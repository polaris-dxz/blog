---
title: 从微信跳一跳学习逆向开发iOS
date: 2017-12-29 17:05:40
tags: iOS
categories:
---

这几天出了个小程序特别火，借此机会学习下逆向开发。
<!-- more -->

[TOC]

## 一、libimobiledevice与 adb

libimobiledevice：逆向出 iOS 与 Mac Windows 接口的通讯协议

adb：安卓下调试工具



## 二、安装libimobiledevice

```sh
$ brew update
$ brew install libimobiledevice
# libimobiledevice中并不包含ipa的安装命令，所以还需要安装
$ brew install ideviceinstaller
```



