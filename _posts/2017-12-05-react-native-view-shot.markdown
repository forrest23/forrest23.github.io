---
title: "React Native 截屏组件"
layout: post
date: 2017-12-05 14:33
image: /assets/images/markdown.jpg
headerImage: false
tag:
- react native
star: false
category: blog
author: forrest23
description: React Native 截屏组件。

---

*本文原创首发于公众号：ReactNative开发圈，转载需注明出处。*

> React Native 截屏组件：react-native-view-shot，可以截取当前屏幕或者按照当前页面的组件来选择截取，如当前页面有一个图片组件，一个View组件，可以选择截取图片组件或者View组件。支持iOS和安卓。  

## 安装方法
```
npm install react-native-view-shot
react-native link react-native-view-shot
```

## 使用示例
### captureScreen()  截屏方法
截取当前屏幕，跟系统自带的截图一致，只会截取当前屏幕显示的页面内容。如果是ScrollView，那么未显示的部分是不会被截取的。
```
import { captureScreen } from "react-native-view-shot";

captureScreen({
  format: "jpg",
  quality: 0.8
})
.then(
  uri => console.log("Image saved to", uri),
  error => console.error("Oops, snapshot failed", error)
);
```

### captureRef(view, options) 根据组件reference名称来截取
```
import { captureRef } from "react-native-view-shot";

render() {
     return (
	 <ScrollView ref="full">
		  <View ref="form1”>
		   </View>
                  <View ref="form2”>
		   </View>
	</ScrollView>
);
}

snapshot = refname => () =>
captureRef(refname, {
  format: "jpg",
  quality: 0.8,
  result: "tmpfile",
  snapshotContentContainer: true
})
.then(
  uri => console.log("Image saved to", uri),
  error => console.error("Oops, snapshot failed", error)
);
```

指定需要截取的组件的ref名称，然后将该ref名称传递给snapshot方法来截取指定组件的内容。如需要截取ScrollView，只需要将”full”传递给snapshot方法即可。
captureRef方法和captureScreen方法都可以设置options，options的说明如下：
width / height：可以指定最后生成图片的宽度和高度。
format：指定生成图片的格式png or jpg or webm (Android). 默认是png。
quality：图片的质量0.0 - 1.0 (default)。
result：最后生成的类型，可以是tmpfile、base64、data-uri。
snapshotContentContainer：如果设置为True的话，会动态计算组件的高度。如果是ScrollView组件，就会截取整个ScrollView的实际高度。

## 支持的组件
![Screenshot](http://pic.yupoo.com/forrest071/GWLb8sOV/DuR1v.png)

## 示例源码
[GitHub - forrest23/ReactNativeComponents: React Native组件大全](https://github.com/forrest23/ReactNativeComponents)

## 组件地址
[GitHub - gre/react-native-view-shot: Snapshot a React Native view and save it to an image](https://github.com/gre/react-native-view-shot)


举手之劳关注我的微信公众号：**ReactNative开发圈**
![Screenshot](http://pic.yupoo.com/forrest071/GW9CBRAi/medium.jpg)
