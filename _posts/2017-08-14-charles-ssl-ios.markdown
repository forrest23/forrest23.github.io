---
title: "Charles在ios10.3下https抓包失败"
layout: post
date: 2017-08-14 10:38
image: /assets/images/markdown.jpg
headerImage: false
tag:
- tool
star: false
category: blog
author: ganyin
description: 提示Received fatal alert unknown_ca
---

## 问题:

今天把苹果系统升级到了10.12.6后，发现在IOS模拟器上的https请求，Charles抓包都失败了。提示Failure SSLHandshake: Received fatal alert: unknown_ca 和You may need to configure your browser or application to trust the Charles Root Certificate。

### IOS模拟器解决方法:
- 首先要把IOS模拟器退出。这一点很重要（我就是没退出，然后证书一直没装成功）。
- 然后打开Charles,选择SSL Proxying > Install Charles Root Certificate in iOS Simulators，这样Charles会把所有的模拟器都安装上证书。
- 然后在你要抓包的https请求上右击，选择Enable SSL Proxying。
- 现在你就可以抓包了。

### IOS真机解决方法:
- 把手机设置Charles的代理。
- 然后用Safari打开https://chls.pro/ssl安装证书。
- 打开通过 > 关于 > 证书信任设置，信任Charles的证书。
- 现在你就可以抓包了。
---