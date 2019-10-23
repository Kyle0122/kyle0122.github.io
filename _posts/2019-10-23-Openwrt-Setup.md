---
title: Openwrt Setup
layout: post
date: 2019-10-23 14:43:00 +0800
---

前一阵买了一个New wifi mini，用的是mt7620的方案，支持2.5G、5GWIFI，刷上了Openwrt 18.06，在这里记录一下刷好系统之后折腾的步骤。

### **1. 设置opkg使用https** ###
Openwrt为了节省空间，默认使用http来下载安装包，如果不设置https的话会有一些污染问题。
```bash
    opkg update
    opkg install ca-certificates libustream-openssl
    vi /etc/opkg/distfeeds.conf
    **然后将distfeeds.conf中的http替换成https**
```

###**2.配置shadowsocks-libev**###

```bash
opk update
opkg install shadowsocks-libev-config shadowsocks-libev-ss-local shadowsocks-libev-ss-redir shadowsocks-libev-ss-rules shadowsocks-libev-ss-tunnel luci-app-shadowsocks-libev

```

进入openwrt web配置界面，选择 Service->shadowsocks-libev
点击 Remote Servers, 里面已经默认配置一个服务器 sss0，修改地址，端口，密码，加密方式，最重要的，将disabled的勾去掉，点击 save&apply 按钮。
再点击 Local Instances, 点击 ss-local.cfgXXXXX (XXX为随机数字)条目对应的Disabled 按钮，将其变成 Enabled，点击 Save & Apply。配置保存生效以后, ss-local.cfgXXXX 条目的Running 状态由no变为yes。这时，路由器上已经运行一个SOCKS5服务器，端口1080。设置电脑浏览器的代理服务器为路由器地址，端口1080，尝试访问谷歌，如果成功则说明ss客户端在openwrt上工作一切正常。
