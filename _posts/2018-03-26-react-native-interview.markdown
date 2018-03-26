---
title: "React Native面试题"
layout: post
date: 2018-03-26 12:53
image: /assets/images/markdown.jpg
headerImage: false
tag:
- react native
star: false
category: blog
author: forrest23
description: React Native面试题。

---
*本文原创首发于公众号：ReactNative开发圈，转载需注明出处。*

# React Native
#ReactNaitve开发圈
## 1.React Native相对于原生的ios和Android有哪些优势？
1.性能媲美原生APP
2.使用JavaScript编码，只要学习这一种语言
3.绝大部分代码安卓和IOS都能共用
4.组件式开发，代码重用性很高
5.跟编写网页一般，修改代码后即可自动刷新，不需要慢慢编译，节省很多编译等待时间
6.支持APP热更新，更新无需重新安装APP

缺点：
内存占用相对更高
版本还不稳定，一直在更新，现在还没有推出稳定的1.0版本

## 2.React Native组件的生命周期
生命周期	调用次数	能否使用 setSate()
getDefaultProps	1(全局调用一次)	否
getInitialState	1	否
componentWillMount	1	是
render	>=1	否
componentDidMount	1	是
componentWillReceiveProps	>=0	是
shouldComponentUpdate	>=0	否
componentWillUpdate	>=0	否
componentDidUpdate	>=0	否
componentWillUnmount	1	否

## 3.当你调用setState的时候，发生了什么事？
当调用 setState 时，React会做的第一件事情是将传递给 setState 的对象合并到组件的当前状态。
这将启动一个称为和解（reconciliation）的过程。
和解（reconciliation）的最终目标是以最有效的方式，根据这个新的状态来更新UI。
为此，React将构建一个新的 React 元素树（您可以将其视为 UI 的对象表示）。
一旦有了这个树，为了弄清 UI 如何响应新的状态而改变，React 会将这个新树与上一个元素树相比较（ diff ）。
通过这样做， React 将会知道发生的确切变化，并且通过了解发生什么变化，只需在绝对必要的情况下进行更新即可最小化 UI 的占用空间。

## 4.props和state相同点和不同点
1.不管是props还是state的改变，都会引发render的重新渲染。
2.都能由自身组件的相应初始化函数设定初始值。

不同点
1.初始值来源：state的初始值来自于自身的getInitalState（constructor）函数；props来自于父组件或者自身getDefaultProps（若key相同前者可覆盖后者）。

2.修改方式：state只能在自身组件中setState，不能由父组件修改；props只能由父组件修改，不能在自身组件修改。

3.对子组件：props是一个父组件传递给子组件的数据流，这个数据流可以一直传递到子孙组件；state代表的是一个组件内部自身的状态，只能在自身组件中存在。

## 5.shouldComponentUpdate 应该做什么
其实这个问题也是跟reconciliation有关系。
“和解（ reconciliation ）的最终目标是以最有效的方式，根据新的状态更新用户界面”。
如果我们知道我们的用户界面（UI）的某一部分不会改变，
那么没有理由让 React 很麻烦地试图去弄清楚它是否应该渲染。
通过从 shouldComponentUpdate 返回 false，
React 将假定当前组件及其所有子组件将保持与当前组件相同

## 6.reactJS的props.children.map函数来遍历会收到异常提示，为什么？应该如何遍历？
this.props.children 的值有三种可能：
    1.当前组件没有子节点，它就是 undefined;
    2.有一个子节点，数据类型是 object ；
    3.有多个子节点，数据类型就是 array 。
系统提供React.Children.map()方法安全的遍历子节点对象

## 7.redux状态管理的流程
action是用户触发或程序触发的一个普通对象。
reducer是根据action操作来做出不同的数据响应，返回一个新的state。
store的最终值就是由reducer的值来确定的。（一个store是一个对象, reducer会改变store中的某些值）
action -> reducer -> 新store -> 反馈到UI上有所改变。

## 8.RN加载脚本的机制
要实现RN的脚本热更新，我们要搞明白RN是如何去加载脚本的。 在编写业务逻辑的时候，我们会有许多个js文件，打包的时候RN会将这些个js文件打包成一个叫index.android.bundle(ios的是index.ios.bundle)的文件，所有的js代码(包括rn源代码、第三方库、业务逻辑的代码)都在这一个文件里，启动App时会第一时间加载bundle文件，所以脚本热更新要做的事情就是替换掉这个bundle文件。

## 9.Flex布局
采用Flex布局的元素，称为Flex容器（flex Container），简称"容器"。它的所有子元素自动成为容器成员，称为Flex项目（flex item），简称"项目"。

容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。主轴的开始位置（与边框的交叉点）叫做main start，结束位置叫做main end；交叉轴的开始位置叫做cross start，结束位置叫做cross end。

项目默认沿主轴排列。单个项目占据的主轴空间叫做main size，占据的交叉轴空间叫做cross size。

容器的属性
以下6个属性设置在容器上。
flex-direction  属性决定主轴的方向（即项目的排列方向)。
flex-wrap   属性定义，如果一条轴线排不下，如何换行。
flex-flow   flex-flow属性是flex-direction属性和flex-wrap属性的简写形式。
justify-content   定义了项目在主轴上的对齐方式。
align-items  属性定义项目在交叉轴上如何对齐。
align-content  align-content属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。

## 10.JS调用原生方法
RCTBridgeModule
RCT_EXPORT_MODULE
RCT_EXPORT_METHOD
RCT_REMAP_METHOD

Promises
Callbacks

11.原生发送事件给JS
RCTEventEmitter
sendEventWithName
NativeEventEmitter


欢迎关注我的微信公众号：**ReactNative开发圈**
![](http://pic.yupoo.com/forrest071/GXPy4uDg/small.jpg)

