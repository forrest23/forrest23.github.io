---
title: "React Native智能提示输入框组件"
layout: post
date: 2018-03-02 14:29
image: /assets/images/markdown.jpg
headerImage: false
tag:
- react native
star: false
category: blog
author: forrest23
description: React Native智能提示输入框组件。

---
*本文原创首发于公众号：ReactNative开发圈，转载需注明出处。*

> React Native智能提示输入框组件：react-native-autocomplete-input，纯JS组件，实现用户在输入后自动提示相似内容，用户可以快捷的选择。

## 效果图
![](http://pic.yupoo.com/forrest071/5faf7aba/1afb8ac4.gif)

## 安装方法
`npm install --save react-native-autocomplete-input`

## 示例代码
```
<View style={styles.container}>
        <Autocomplete
          autoCapitalize="none"
          autoCorrect={false}
          containerStyle={styles.autocompleteContainer}
          data={films.length === 1 && comp(query, films[0].title) ? [] : films}
          defaultValue={query}
          onChangeText={text => this.setState({ query: text })}
          placeholder="输入星球大战电影名称"
          renderItem={({ title, release_date }) => (
            <TouchableOpacity onPress={() => this.setState({ query: title })}>
              <Text style={styles.itemText}>
                {title} ({release_date.split('-')[0]})
              </Text>
            </TouchableOpacity>
          )}
        />
        <View style={styles.descriptionContainer}>
          {films.length > 0 ? (
            Component07.renderFilm(films[0])
          ) : (
            <Text style={styles.infoText}>
              输入星球大战电影名称
            </Text>
          )}
        </View>
      </View>
```

## 主要参数说明
* containerStyle  组件所在容器的样式
* hideResults 当为true时隐藏自动提示
* data 自动提示数据源（数组）
* inputContainerStyle input组件所在容器的样式
* listContainerStyle list组件所在容器的样式
* listStyle  list样式
* renderItem 设置提示项
* renderTextInput 自定义Input

## 完整示例
完整代码：[GitHub - forrest23/ReactNativeComponents: React Native组件大全，介绍React Native常用组件的使用方法和使用示例](https://github.com/forrest23/ReactNativeComponents)
本次示例代码在 Component07文件夹中。**请不要吝啬你们的Star**！

## 组件地址
[GitHub - l-urence/react-native-autocomplete-input: Pure javascript autocomplete input for react-native](https://github.com/l-urence/react-native-autocomplete-input)

**微信不让跳转外链，可以点击查看原文来查看外链GitHub内容。**

举手之劳关注我的微信公众号：**ReactNative开发圈**
![](http://pic.yupoo.com/forrest071/GXPy4uDg/small.jpg)

