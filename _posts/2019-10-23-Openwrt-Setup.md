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
