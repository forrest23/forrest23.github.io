---
title: "React Native 弹出框组件"
layout: post
date: 2018-01-19 10:59
image: /assets/images/markdown.jpg
headerImage: false
tag:
- react native
star: false
category: blog
author: forrest23
description: React Native 弹出框组件。

---
*本文原创首发于公众号：ReactNative开发圈，转载需注明出处。*

> React Native 弹出框组件：react-native-popup-dialog，纯JS组件，支持动画，支持iOS和Android，安装使用方便。

## 演示动画
![](http://pic.yupoo.com/forrest071/f83ea60f/9e910195.gif)

## 安装方法
`npm install --save react-native-popup-dialog`


## 使用示例
```
import PopupDialog, { SlideAnimation } from 'react-native-popup-dialog';

const slideAnimation = new SlideAnimation({
  slideFrom: 'bottom',
});

<View style={styles.container}>
  <PopupDialog
    ref={(popupDialog) => { this.popupDialog = popupDialog; }}
    dialogAnimation={slideAnimation}
  >
    <View>
      <Text>Hello</Text>
    </View>
  </PopupDialog>
</View>
```

支持三种动画：FadeAnimation（淡入淡出）、ScaleAnimation（缩放）、SlideAnimation（滑动）

##  API说明
* dialogTitle – 弹出框标题
* width - 弹出框的宽度，可以写300或者0.5。0.5就是设备宽度的50%
* height - 弹出框的宽度，可以写300或者0.5。0.5就是设备高度的50%
* dialogAnimation - 动画类型，FadeAnimation、ScaleAnimation、SlideAnimation
* haveOverlay - 是否显示Overlay
* dismissOnTouchOutside - 点击外部是否关闭弹出框
* show - 显示弹出框

## 完整示例
完整代码：[GitHub - forrest23/ReactNativeComponents: React Native组件大全，介绍React Native常用组件的使用方法和使用示例](https://github.com/forrest23/ReactNativeComponents)
本次示例代码在 Component04文件夹中。请不要吝啬你们的Star！

## 组件地址
[GitHub - jacklam718/react-native-popup-dialog: A React Native Popup Dialog Easy Use & Support Custom Animation. For IOS & Android.](https://github.com/jacklam718/react-native-popup-dialog)

**微信不让跳转外链，可以点击查看原文来查看外链GitHub内容。**

举手之劳关注我的微信公众号：**ReactNative开发圈**
![](http://pic.yupoo.com/forrest071/GW9CBRAi/medium.gif)
