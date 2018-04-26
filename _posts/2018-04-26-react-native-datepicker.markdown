---
title: "React Native日期时间选择组件"
layout: post
date: 2018-04-26 09:35
image: /assets/images/markdown.jpg
headerImage: false
tag:
- react native
star: false
category: blog
author: forrest23
description: React Native日期时间选择组件

---
*本文原创首发于公众号：ReactNative开发圈，转载需注明出处。*

# 首先祝大家劳动节快乐，劳动最光荣！
> React Native日期时间选择组件：react-native-datepicker，支持安卓和IOS双平台，支持单独选择日期、单独选择时间和选择日期和时间，支持自定义日期格式。  

## 效果图
![](http://pic.yupoo.com/forrest071/7c4b145f/cb633c17.gif)

## 安装方法
```
npm install react-native-datepicker --save
```

## 示例代码
```
<Text style={styles.instructions}>time: {this.state.time}</Text>
        <DatePicker
          style={{width: 200}}
          date={this.state.datetime}
          mode="datetime"
          format="YYYY-MM-DD HH:mm"
          confirmBtnText="确定"
          cancelBtnText="取消"
          showIcon={false}
          onDateChange={(datetime) => {this.setState({datetime: datetime});}}
        />
        <Text style={styles.instructions}>datetime: {this.state.datetime}</Text>
        <DatePicker
          style={{width: 200}}
          date={this.state.datetime1}
          mode="datetime"
          format="YYYY-MM-DD HH:mm"
          confirmBtnText="确定"
          cancelBtnText="取消"
          minuteInterval={10}
          onDateChange={(datetime) => {this.setState({datetime1: datetime});}}
        />
        <Text style={styles.instructions}>datetime: {this.state.datetime1}</Text>
```

## 主要参数说明
date：设置初始显示的日期
mode：显示的模式，date,datetime,time
format：设置日期格式，默认为'YYYY-MM-DD'
confirmBtnText：确定按钮的显示名称
cancelBtnText：取消按钮的显示名称
minDate：显示的最小日期
maxDate：显示的最大日期
duration：时间间隔
onDateChange：日期变化时触发的事件
placeholder：占位符

## 完整示例
完整代码：[GitHub - forrest23/ReactNativeComponents: React Native组件大全，介绍React Native常用组件的使用方法和使用示例](https://github.com/forrest23/ReactNativeComponents)
本次示例代码在 Component11文件夹中。**请不要吝啬你们的Star**！

## 组件地址
[GitHub - xgfe/react-native-datepicker: react native datePicker component for both Android and IOS, useing DatePikcerAndroid, TimePickerAndroid and DatePickerIOS](https://github.com/xgfe/react-native-datepicker)

**微信不让跳转外链，可以点击查看原文来查看外链GitHub内容。**

欢迎关注我的微信公众号：**ReactNative开发圈**
![](http://pic.yupoo.com/forrest071/GXPy4uDg/small.jpg)