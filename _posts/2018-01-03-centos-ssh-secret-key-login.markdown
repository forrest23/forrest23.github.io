---
title: "腾讯云CentOS使用SSH密钥登陆"
layout: post
date: 2017-12-05 14:33
image: /assets/images/markdown.jpg
headerImage: false
tag:
- CentOS
star: false
category: blog
author: forrest23
description: 腾讯云CentOS使用SSH密钥登陆。

---
*本文原创首发于公众号：ReactNative开发圈，转载需注明出处。*

> 最近刚买了一台腾讯云的CentOS服务器，刚用一天就发现有人在暴力破解root密码，破解次数很高，已经有几千次。看了下腾讯云是支持SHH密钥登陆的，所以就折腾了下。  

## 服务器端设置
腾讯云后台是可以直接设置SHH密钥，然后再绑定相应的服务器的。首先我们要先生成自己的密钥，这样更加安全点。

![](http://pic.yupoo.com/forrest071/6f4772ca/8a237d02.png)

### 本地生成密钥
`ssh-keygen -t rsa`

这一条命令即可，执行后，首先会问你将密钥保存在哪里，这里可以直接按回车，然后让设置密钥密码，需要输入两次。然后密钥就生成成功了。然后会告诉你密钥文件保存的位置，找到指定的位置，打开.pub的文件，这个就是公钥，复制里面的所有内容，等会有用。
![](http://pic.yupoo.com/forrest071/11a899ea/92de8514.jpg)

### 将公钥复制到腾讯云上
首先登陆到腾讯云后台，然后到云服务器管理界面，点击SSH密钥。然后点击创建密钥，选择使用自己的公钥。
![](http://pic.yupoo.com/forrest071/02a12fde/27ba25b3.png)
然后将刚刚复制的内容粘贴到公钥中，密钥名称可以随便填写，然后点击确定。
![](http://pic.yupoo.com/forrest071/0bce6590/b853dafb.png)
然后需要将主机关机，然后选择这条密钥点击绑定主机，选择你需要绑定的主机，等待设置完成，服务器端就设置完成了。

## 本地SSH设置
### 导入公钥认证文件
`cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys`

### 修改mac下的配置文件
```
Host test
Hostname 192.168.11.11
Port 22
User root
IdentityFile ~/.ssh/id_rsa
```

Host 可以自己随便定义
Hostname 改成自己CentOS主机的IP地址
Port 和 User 按照你实际情况修改
IdentityFile 是私钥文件的位置

### 设置自动passphrase
`ssh-add`
执行上面的命令，然后输入生成密钥时输入的密码，这样以后就可以直接登录了。不需要输入任何密码，直接使用密钥登录了。

## SHH密钥登录方法
`ssh test`
直接输入这个就能登陆了。 test 是你自己设置的Host名称。




举手之劳关注我的微信公众号：**ReactNative开发圈**
![Screenshot](http://pic.yupoo.com/forrest071/GW9CBRAi/medium.jpg)
