---
title: "React Native二维码生成组件"
layout: post
date: 2018-03-20 16:48
image: /assets/images/markdown.jpg
headerImage: false
tag:
- react native
star: false
category: blog
author: forrest23
description: React Native二维码生成组件。

---
*本文原创首发于公众号：ReactNative开发圈，转载需注明出处。*

> React Native二维码生成组件：react-native-qrcode，纯JS组件，支持安卓和IOS双平台，支持中文和英文，可以自定义尺寸、前景色和背景色。  

## 效果图
![](http://pic.yupoo.com/forrest071/a73642c3/56efce67.gif)

## 安装方法
`npm install react-native-qrcode --save`

## 示例代码
```
import React, { Component } from 'react';
import QRCode from 'react-native-qrcode';

import { AppRegistry, StyleSheet, View, TextInput, Dimensions } from 'react-native';

export default class Component09 extends Component {
  static navigationOptions = ({ navigation }) => ({
    title: `${navigation.state.params.name}`,
  });

  state = {
    text: 'https://github.com/forrest23/ReactNativeComponents',
  };

  render() {
    return (
      <View style={styles.container}>
        <TextInput
          style={styles.input}
          onChangeText={text => this.setState({ text: text })}
          value={this.state.text}
        />
        <QRCode
          value={this.state.text}
          size={200}
          bgColor="purple"
          fgColor="white"
        />
      </View>
    );
  }
}
```

## 主要参数说明
value：二维码的值
size：大小，默认128
bgColor：背景色，默认#000
fgColor：前景是，默认#fff

## 完整示例
完整代码：[GitHub - forrest23/ReactNativeComponents: React Native组件大全，介绍React Native常用组件的使用方法和使用示例](https://github.com/forrest23/ReactNativeComponents)
本次示例代码在 Component09文件夹中。**请不要吝啬你们的Star**！

## 组件地址
[GitHub - cssivision/react-native-qrcode: a minimalist qrcode component for  react-native](https://github.com/cssivision/react-native-qrcode)

**微信不让跳转外链，可以点击查看原文来查看外链GitHub内容。**

欢迎关注我的微信公众号：**ReactNative开发圈**
![](http://pic.yupoo.com/forrest071/GXPy4uDg/small.jpg)

