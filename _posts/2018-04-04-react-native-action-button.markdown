---
title: "React Native虚浮按钮组件"
layout: post
date: 2018-04-04 14:35
image: /assets/images/markdown.jpg
headerImage: false
tag:
- react native
star: false
category: blog
author: forrest23
description: React Native虚浮按钮组件

---
*本文原创首发于公众号：ReactNative开发圈，转载需注明出处。*

> React Native虚浮按钮组件：react-native-action-button，纯JS组件，支持安卓和IOS双平台，支持设置子按钮，支持自定义位置和样式和图标。  

## 效果图
![](http://pic.yupoo.com/forrest071/46bfb56f/b0dfb20f.gif)

## 安装方法
```
npm i react-native-action-button --save
react-native link react-native-vector-icons
```
因为用到了react-native-vector-icons图标组件，需要做下link。如果你项目中已经使用了react-native-vector-icons，那就不需要这步了。

## 示例代码
```
<View style={styles.container}>
        <Text style={styles.welcome}>
          悬浮按钮组件示例
        </Text>
        <ActionButton buttonColor="rgba(231,76,60,1)" position='left' verticalOrientation='up'>
          <ActionButton.Item buttonColor='#9b59b6' title="New Task" onPress={() => console.log("notes tapped!")}>
            <Icon name="ios-create-outline" style={styles.actionButtonIcon} />
          </ActionButton.Item>
          <ActionButton.Item buttonColor='#3498db' title="Notifications" onPress={() => {}}>
            <Icon name="ios-notifications-off" style={styles.actionButtonIcon} />
          </ActionButton.Item>
          <ActionButton.Item buttonColor='#1abc9c' onPress={() => {}}>
            <Icon name="ios-done-all-outline" style={styles.actionButtonIcon} />
          </ActionButton.Item>
        </ActionButton>

        <ActionButton
          buttonColor="rgba(231,76,60,1)"
          onPress={() => { alert('你点了我！')}}
          renderIcon={() => (<View style={styles.actionButtonView}><Icon name="ios-create-outline" style={styles.actionButtonIcon} />
          <Text style={styles.actionButtonText}>新增</Text>
          </View>)}
        />
      </View>
```

## 主要参数说明
### ActionButton
size：按钮的大小，默认为56
active：是否显示按钮
position：按钮的位置，可以为left center right
offsetX：X轴上的偏移位置
offsetY：Y轴上的偏移位置
onPress：点击事件
onLongPress：长按事件
buttonText：按钮标题
verticalOrientation：弹出按钮的方向，up 或者 down
renderIcon：可以自定义按钮显示的样式，默认是一个加号

### ActionButton.Item
size：按钮的大小，默认为56
title：按钮标题
buttonColor：按钮颜色
onPress：点击事件

## 完整示例
完整代码：[GitHub - forrest23/ReactNativeComponents: React Native组件大全，介绍React Native常用组件的使用方法和使用示例](https://github.com/forrest23/ReactNativeComponents)
本次示例代码在 Component10文件夹中。**请不要吝啬你们的Star**！

## 组件地址
[GitHub - mastermoo/react-native-action-button: customizable multi-action-button component for react-native](https://github.com/mastermoo/react-native-action-button)

**微信不让跳转外链，可以点击查看原文来查看外链GitHub内容。**

欢迎关注我的微信公众号：**ReactNative开发圈**
![](http://pic.yupoo.com/forrest071/GXPy4uDg/small.jpg)