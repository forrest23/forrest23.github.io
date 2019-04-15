---
title: "React Native 使用自定义字体"
layout: post
date: 2019-04-15 15:27
image: /assets/images/markdown.jpg
headerImage: false
tag:
- react native
star: false
category: blog
author: forrest23
description: React Native 使用自定义字体

---
**本文原创首发于公众号：ReactNative开发圈，转载需注明出处。**

## 下载字体文件
先下载你需要的字体文件，注意后缀要是ttf的,如下图所示
![](http://pic.yupoo.com/3rbang/5d993076/8c147cef.png)

## 把字体文件添加到Assets
然后在你的react native项目根目录中添加assets/fonts文件夹，然后将字体文件拷贝进来
![](http://pic.yupoo.com/3rbang/6ea2d5fb/a48640c8.png)

## 编辑Package.json
编辑根目录的Package.json文件，在其中添加下面的代码：
```
  "rnpm": {
    "assets": [
      "./assets/fonts/"
    ]
  },
```
具体文件夹的名称根据你添加的字体文件夹来定。

## link字体文件
执行下面的命令，让react native自动帮我们link字体文件
```
react-native link
```
这样自定义字体就添加完成了。

## 使用自定义字体
```
instructions: {
    fontFamily: "PingFangSC-Medium",
    fontSize: 20,
    textAlign: "center",
    color: "#333333",
    marginBottom: 5
  }
```
只有在fontFamily中指定你添加的字体名称即可


欢迎关注我的微信公众号：**ReactNative开发圈**
![](http://pic.yupoo.com/forrest071/GXPy4uDg/small.jpg)