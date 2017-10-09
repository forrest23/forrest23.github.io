---
title: "React Native WebView在安卓中网页打开显示空白"
layout: post
date: 2017-10-09 11:05
image: /assets/images/markdown.jpg
headerImage: false
tag:
- React Native
star: false
category: blog
author: ganyin
description: React Native WebView在安卓中网页打开显示空白,在苹果上打开显示正常

---

## 问题:

今天在我们需要在APP中嵌入一个新的网页，使用WebView，在苹果中显示正常，但是在安卓手机上打开就是空白页面。跟踪后发现页面请求是正常的，但是就是显示不出来网页。我们用的React Native版本是0.30.0。使用最新的0.44版本测试安卓是可以正常显示的。

经过一番搜索和跟踪后发现，造成问题的原因可能是网页的父级容器的高度设置的是100%，或者没有设置高度，但是在安卓的WebView下不识别100%。

---

## 解决方式:

### 1.修改网页:

如果可以修改网页源码，那么只要将容器的高度设为固定高度即可。这种解决方法比较粗暴。如果网页不能设为固定高度，那么可以使用第二种方法来解决。

### 2.向页面注入js代码:

通过注入JS代码，来动态改变容器的高度。示例代码如下：

{% highlight html %}
const jsForInjection = `
  var el = document.getElementsByTagName('body')[0];
  el.style.height = '${Dimensions.get('window').height}px';
`

<WebView style={styles.webview_style}
                 source={{uri:DEFAULT_URL}}
                 startInLoadingState={true}
                 domStorageEnabled={true}
                 javaScriptEnabled={true}
                 injectJavaScript={jsForInjection}
        >
</WebView>
{% endhighlight %}

---