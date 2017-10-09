---
title: "CentOS7.0在Mac中用SSH连接失败"
layout: post
date: 2017-08-29 09:26
image: /assets/images/markdown.jpg
headerImage: false
tag:
- CentOS
star: false
category: blog
author: ganyin
description: Mac中用SSH连接失败，提示Connection reset by 192.168.58.129 port 22

---

## 问题:

今天新安装了一个CentOS7.0，使用的是最简单的配置，装完配置完固定IP后，发现用mac，shh连接不上，提示Connection reset by 192.168.58.129 port 22。但是在windows下面用软件putty却可以连接的，说明CentOS安装配置是正常。问题应该出在Mac上面的SSH配置上。

---

## 解决:
为了弄清楚更深层次的原因，我们使用命令

{% highlight html %}
ssh -v username@sub.domain.com
{% endhighlight %}

来连接CentOS，挖掘出深层次的原因为

{% highlight html %}
debug1: expecting SSH2_MSG_KEX_DH_GEX_REPLY
{% endhighlight %}

用这个关键字来搜索，最终找到的解决方案为：

**修改/etc/ssh/ssh_config配置，修改完需要退出终端再连接即可**。

ssh_config配置文件修改为如下：
{% highlight html %}
Host *
Ciphers aes128-ctr,aes192-ctr,aes256-ctr,arcfour256,arcfour128,aes128-cbc,3des-cbc
MACs hmac-md5,hmac-sha1,umac-64@openssh.com,hmac-ripemd160
SendEnv LANG LC_*
HashKnownHosts yes
GSSAPIAuthentication yes
GSSAPIDelegateCredentials no
HostKeyAlgorithms ssh-rsa,ssh-dss
{% endhighlight %}

---

## 参考:

- [http://blog.csdn.net/taolinke/article/details/50472557](http://blog.csdn.net/taolinke/article/details/50472557)
- [https://superuser.com/questions/568891/ssh-works-in-putty-but-not-terminal](https://superuser.com/questions/568891/ssh-works-in-putty-but-not-terminal)