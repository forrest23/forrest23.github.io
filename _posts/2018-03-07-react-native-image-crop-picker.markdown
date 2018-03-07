---
title: "React Native图片选择裁剪组件"
layout: post
date: 2018-03-07 17:09
image: /assets/images/markdown.jpg
headerImage: false
tag:
- react native
star: false
category: blog
author: forrest23
description: React Native图片选择裁剪组件。

---
*本文原创首发于公众号：ReactNative开发圈，转载需注明出处。*

> React Native图片选择裁剪组件：react-native-image-crop-picker，支持安卓和IOS双平台，支持从相册、相机选择图片和视频，可以单选和多选，可以压缩和裁剪。  

## 效果图
![](http://pic.yupoo.com/forrest071/5be4255d/1bc05465.gif)

## 安装方法
```
npm i react-native-image-crop-picker --save
react-native link react-native-image-crop-picker
```

如果需要操作视频，需要安装
```
npm i react-native-video --save
react-native link react-native-video
```

因为需要操作相册和相机，IOS需要增加隐私访问说明，修改info.plist文件增加以下项：
```
	<key>NSPhotoLibraryUsageDescription</key>
	<string>此 App 需要您的同意才能读取相册</string>
	<key>NSCameraUsageDescription</key>
	<string>此 App 需要您的同意才能使用相机</string>
```

## 示例代码
### 从相册选择单个图片并裁剪
```
ImagePicker.openPicker({
  width: 300,
  height: 400,
  cropping: true
}).then(image => {
  console.log(image);
});
```

### 从相册选择多个图片
```
ImagePicker.openPicker({
  multiple: true
}).then(images => {
  console.log(images);
});
```

### 从相册选择视频
```
ImagePicker.openPicker({
  mediaType: "video",
}).then((video) => {
  console.log(video);
});
```

### 从相机选择图片
```
ImagePicker.openCamera({
  width: 300,
  height: 400,
  cropping: true
}).then(image => {
  console.log(image);
});
```

### 裁剪图片
```
ImagePicker.openCropper({
  path: 'my-file-path.jpg',
  width: 300,
  height: 400
}).then(image => {
  console.log(image);
});
```

## 主要参数说明
* cropping  是否进行裁剪 bool (default false)
* width 裁剪图片的宽度
* height 裁剪图片的高度
* multiple 是否多选  bool (default false)
* includeBase64 是否返回Base64的图片数据 bool (default false)
* mediaType  媒体类别  'photo', 'video', or 'any'
* cropperCircleOverlay 使用圆形遮盖裁剪

## 完整示例
完整代码：[GitHub - forrest23/ReactNativeComponents: React Native组件大全，介绍React Native常用组件的使用方法和使用示例](https://github.com/forrest23/ReactNativeComponents)
本次示例代码在 Component08文件夹中。**请不要吝啬你们的Star**！

## 组件地址
[GitHub - ivpusic/react-native-image-crop-picker: iOS/Android image picker with support for camera, configurable compression, multiple images and cropping](https://github.com/ivpusic/react-native-image-crop-picker)

**微信不让跳转外链，可以点击查看原文来查看外链GitHub内容。**

举手之劳关注我的微信公众号：**ReactNative开发圈**
![](http://pic.yupoo.com/forrest071/GXPy4uDg/small.jpg)

