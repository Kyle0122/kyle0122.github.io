---
layout: post
title: "Archlinux maintance总结"
date: 2018-02-17 16:20:00 -0800
---

今天下午折腾Arch(之前更新包的时候断电了)总结一下学到的一些pacman用法。

1.有些时候系统会产生几个孤立(orphans)包，它们已经在arch源(以及各类repo)里找不到了。

删掉的方法很简单:
{% highlight bash %}
显示孤立包
$ pacman -Qtdq
递归删除
$ pacman -Rs $(pacman -Qtdq)
{% endhighlight bash %}

2.Archlinux 不支持部分升级，一定要全部更新

3.备份已安装包列表的方法
{% highlight bash %}
列出除了base base-devel 之外的软件包：
$ comm -23 <(pacman -Qeq|sort) <(pacman -Qgq base base-devel|sort)
列出非本地的软件包：
$ comm -23 <(pacman -Qeq|sort) <(pacman -Qmq|sort)
{% endhighlight bash %}

4.安装(更新)时断电，我得到了一大堆ldconfig: xxxx is empty ....错误，解决办法是一个个找到对应的软件包并重装。

{% highlight bash %}
查询对应.so文件的软件包名
$ pacman -Fo /usr/lib/....
强制重装
$ pacman -S --force ....
{% endhighlight bash %}

参考：

[pacman:Tips&tricks简体中文](https://wiki.archlinux.org/index.php/Pacman/Tips_and_tricks_(简体中文)). <br>
[pacman:Tips&tricks](https://wiki.archlinux.org/index.php/Pacman/Tips_and_tricks)

[Archlinux System_maintenance](https://wiki.archlinux.org/index.php/System_maintenance)

[Archlinux pacman](https://wiki.archlinux.org/index.php/Pacman)

[pacman 简体中文](https://wiki.archlinux.org/index.php/Pacman_(简体中文))

[[Solved]Pacman, "is empty, not checked"](https://bbs.archlinux.org/viewtopic.php?id=215731)
