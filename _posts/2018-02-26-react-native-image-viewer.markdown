---
title: "React Native 图片查看组件"
layout: post
date: 2018-02-28 16:03
image: /assets/images/markdown.jpg
headerImage: false
tag:
- react native
star: false
category: blog
author: forrest23
description: React Native 图片查看组件。

---
*本文原创首发于公众号：ReactNative开发圈，转载需注明出处。*

# 新的一年，新的开始，祝大家旺旺年旺旺旺！
> React Native 图片查看组件：react-native-image-viewer，纯JS组件，小巧快速的图标查看组件。支持图片放大缩小，支持图片加载失败设置替代图片，支持将图片保存到本地等功能。  

## 效果图
![](http://pic.yupoo.com/forrest071/bfe00368/d96a21ae.gif)

## 安装方法
`npm i react-native-image-zoom-viewer --save`

## 使用示例
```
const images = [
  {
    url: 'https://avatars2.githubusercontent.com/u/7970947?v=3&s=460',
  },
  {
    url: 'https://avatars2.githubusercontent.com/u/7970947?v=3&s=460',
  },
  {
    url: 'https://avatars2.githubusercontent.com/u/7970947?v=3&s=460',
  },
];

export default class Component06 extends Component {
  constructor(props) {
    super(props);
  }

  render() {
    return (
      <View style={{ flex: 1 }}>
        <ImageViewer
          imageUrls={images}
          failImageSource={{
            url: 'https://avatars2.githubusercontent.com/u/7970947?v=3&s=460',
            width: Dimensions.get('window').width,
            height: Dimensions.get('window').width,
          }}
        />
      </View>
    );
  }
}
```

## 主要参数说明
* imageUrls 图片url地址的数组
* enableImageZoom 是否允许缩放
* failImageSource 加载失败时显示的图片
* loadingRender 加载loading
* renderHeader 头部样式
* renderFooter  底部样式
* renderIndicator 页码指示器样式

## 完整示例
完整代码：[https://github.com/forrest23/ReactNativeComponents](https://github.com/forrest23/ReactNativeComponents)
本次示例代码在 Component06文件夹中。***请不要吝啬你们的Star***！

## 组件地址
[https://github.com/ascoders/react-native-image-viewer](https://github.com/ascoders/react-native-image-viewer)

**微信不让跳转外链，可以点击查看原文来查看外链GitHub内容。**

举手之劳关注我的微信公众号：**ReactNative开发圈**
![](http://pic.yupoo.com/forrest071/GW9CBRAi/medium.gif)

