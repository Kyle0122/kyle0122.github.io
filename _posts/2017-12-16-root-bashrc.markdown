---
layout: post
title: "root bashrc"
date: 2017-12-16 00:42:00 -0800
---

.bashrc is not working with root user,
but you can use ~/.bash_profile instead.

{% highlight bash %}
#
# ~/.bash_profile
#

# If not running interactively, don't do anything
[[ $- != *i* ]] && return
echo "Hello Root"

alias ls='ls --color=always'
alias ll='ls -al --color=always'
PS1='[\u@\h \W]\$ '
{% endhighlight bash %}

The only problem is that .bash_profile will not be executed when you login using ssh.
