---
title: "React Native 表格组件"
layout: post
date: 2018-02-08 16:56
image: /assets/images/markdown.jpg
headerImage: false
tag:
- react native
star: false
category: blog
author: forrest23
description: React Native 表格组件。

---
*本文原创首发于公众号：ReactNative开发圈，转载需注明出处。*

> React Native 表格组件：react-native-data-table，纯JS组件，功能强大。支持自定义表头、行、单元格样式。支持编辑单元格和选择列。还能显示子行。  

## 效果图
![](http://pic.yupoo.com/forrest071/faa06aee/8b121557.png)

## 安装方法
`npm install --save react-native-data-table`

## 组件说明
### 表格组件主要分成以下几部分：
DataTable  表格
HeaderCell 列头
Row 行
Cell  单元格
CheckableCell 可选择单元格
EditableCell 可编辑单元格
Expansion  子行
其他使用方法类似于官方的ListView组件

## 使用示例
```
import {
  Cell,
  DataTable,
  Header,
  HeaderCell,
  Row,
  EditableCell,
  CheckableCell,
} from 'react-native-data-table';

render() {
    return (
      <View style={styles.container}>
        <DataTable
          style={styles.container}
          listViewStyle={styles.container}
          dataSource={this.state.ds}
          renderRow={this.renderRow}
          renderHeader={this.renderHeader}
        />
      </View>
    );
  }
  
  renderHeader() {
    return (
      <Header>
        <HeaderCell style={styles.headerCell} key="1" text="选择" width={1} />
        <HeaderCell
          style={styles.headerCell}
          key="2"
          text="序号"
          width={1}
          onPress={() => this.onColumnSort()}
        />
        <HeaderCell
          style={styles.headerCell}
          key="3"
          text="科室名称"
          width={3}
          isAscending={false}
          onPress={() => this.onColumnSort()}
        />
        <HeaderCell
          style={styles.headerCell}
          key="4"
          text="数量"
          width={1}
          isAscending={false}
          onPress={() => this.onColumnSort()}
        />
      </Header>
    );
  }

  renderRow(item) {
    let rowStyle = item.no%2 === 0  ? styles.whiteRow : styles.row;
    return (
      <Row style={rowStyle}>
        <CheckableCell
          style={styles.cell}
          width={1}
          onPress={() => this.onCheckablePress()}
          renderIsChecked={() => (
            <Icon name="checkbox-blank-outline" size={20} color="blue" />
          )}
          renderIsNotChecked={() => (
            <Icon name="checkbox-marked" size={20} color="blue" />
          )}
          isChecked={item.isChecked}
        />
        <Cell style={styles.cell} width={1}>
          {item.no}
        </Cell>
        <Cell style={styles.cell} width={3}>
          {item.name}
        </Cell>
        <EditableCell width={1} value={item.qty} onEndEditing={(target, value) => {}}>
        </EditableCell>
      </Row>
    );
  }

  onCheckablePress() {}

  onColumnSort() {}
```

## 完整示例
完整代码：[](https://github.com/forrest23/ReactNativeComponents)
本次示例代码在 Component05文件夹中。***请不要吝啬你们的Star***！

## 组件地址
[](https://github.com/sussol/react-native-data-table)

**微信不让跳转外链，可以点击查看原文来查看外链GitHub内容。**

举手之劳关注我的微信公众号：**ReactNative开发圈**
![](http://pic.yupoo.com/forrest071/GW9CBRAi/medium.gif)
