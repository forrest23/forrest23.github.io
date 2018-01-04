---
title: "React Native 圆形进度条组件"
layout: post
date: 2018-01-04 09:10
image: /assets/images/markdown.jpg
headerImage: false
tag:
- react native
star: false
category: blog
author: forrest23
description: React Native 圆形进度条组件。

---
*本文原创首发于公众号：ReactNative开发圈，转载需注明出处。*

> React Native 圆形进度条组件：react-native-circular-progress，圆形的进度条组件，支持动画，支持iOS和Android。  

## 演示动画
![](http://pic.yupoo.com/forrest071/97d85b21/810c50fe.gif)

## 安装方法
`npm i --save react-native-circular-progress`

IOS需要手动Link下ReactART，用Xcode打开项目，添加ART.xcodeproj到Libraries中，然后在Link Binary With Libraries中添加libART.a。如下图所示：
![](http://pic.yupoo.com/forrest071/66f1f1ab/81dd9a6d.png)


## 使用示例
```
import { AnimatedCircularProgress } from 'react-native-circular-progress';

<AnimatedCircularProgress
  size={120}
  width={15}
  fill={100}
  tintColor="#00e0ff"
  onAnimationComplete={() => console.log('onAnimationComplete')}
  backgroundColor="#3d5875" />
```

##  API说明
* size – width and height of the circle（圆形的宽度和高度）
* width - thickness of the lines（圆形线的宽度）
* backgroundWidth - thickness of the background line（背景线的宽度）
* fill - current, percentage fill (from 0 to 100)（进度值）
* prefill - percentage fill before the animation (from 0 to 100)（预先设置的进度值）
* tintColor - color of a progress line（圆形的线的颜色）
* backgroundColor - color of a background for progress line. Use 'transparent' to hide(背景线的颜色）
* rotation - by default, progress starts from the angle = 90⦝, you can change it by setting value from -360 to 360(旋转度数)
* tension - the tension value for the spring animation (see here)
* friction - the friction value for the spring animation (see here)
* linecap - the shape to be used at the ends of the circle. Possible values: butt (default), round or square. (see here)
* children(fill) - you can pass function as a child to receive current fill
* onAnimationComplete - you can pass a callback function that will be invoked when animation is complete. (see here)(动画结束时的事件)
* onLinearAnimationComplete - you can pass a callback function that will be invoked when linear animation is complete. (see here)

## 特别说明
在react-native 0.50.4版本中，backgroundColor设置transparent时会报错。暂时没找到原因。

## 完整示例
完整代码：[React Native 圆形进度条组件 | forrest23.github.io](http://codeismoney.com/react-native-circular-progress/)
本次示例代码在 Component03文件夹中。

## 组件地址
[GitHub - bgryszko/react-native-circular-progress: React Native component for creating animated, circular progress with ReactART](https://github.com/bgryszko/react-native-circular-progress)

**微信不让跳转外链，可以点击查看原文来查看外链GitHub内容。**

举手之劳关注我的微信公众号：**ReactNative开发圈**
![](http://pic.yupoo.com/forrest071/GW9CBRAi/medium.gif)
