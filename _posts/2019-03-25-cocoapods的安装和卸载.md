---
layout: post
title:  Pod安装与卸载
date:   2019-03-25 00:00:00 +0800
categories: Pods
tag: 教程
---

* content
{:toc}
###pod安装与卸载


####一、安装

1、配置ruby环境

查询 `gem sources -l`

从网上查询最新ruby源，进行替换

比如 

```
gem sources --add https://gems.ruby-china.com/ --remove https://gems.ruby-china.org/ 

```

再次查询是否一致


2、之前使用 `$sudo gem install cocoapods`可以直接安装，现在会报错。
```
While executing gem ... (Gem::FilePermissionError)
    You don't have write permissions for the /usr/bin directory.
```

现在使用 sudo gem install -n /usr/local/bin cocoapods  即可

 
 

####二、卸载

使用 $sudo gem uninstall cocoapods

或者 $sudo gem uninstall -n /usr/local/bin cocoapods 

查看本地安装过的与cocoapods的相关的东西

$gem list --local | grep cocoapods

cocoapods-deintegrate (1.0.1)

cocoapods-downloader (1.1.3)

cocoapods-plugins (1.0.0)

cocoapods-search (1.0.0)

cocoapods-stats (1.0.0)

cocoapods-trunk (1.3.0)

cocoapods-try (1.1.0)

逐个删除

$ sudo gem uninstall cocoapods-core

$ sudo gem uninstall cocoapods-deintegrate

...




 
