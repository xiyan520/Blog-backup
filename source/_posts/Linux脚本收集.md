---
title: Linux脚本收集
cover: https://flie.pigax.cn/2022/09/07/631848686a880.jpg
abbrlink: c6026d1a
date: 2022-09-04 16:10:26
updated: 2022-09-04 16:10:26
description: Linux脚本收集
keywords: 花语阁-Linux脚本收集
categories: 网络仓库
tags: [Linux,脚本]
---
> 本文章只用于备份Linux脚本

# Linux系统类

## Linux多合一测试脚本

{% tabs test2,2 %}
<!-- tab 下载-->
```LINUX
wget -O box.sh https://raw.githubusercontent.com/BlueSkyXN/SKY-BOX/main/box.sh && chmod +x box.sh && clear && ./box.sh
```
<!-- endtab -->

<!-- tab 功能预览-->
![功能预览图](https://flie.pigax.cn/2022/09/07/631846272c021.jpg)
<!-- endtab -->

<!-- tab 项目地址-->
{% ghcard BlueSkyXN/SKY-BOX %}
<!-- endtab -->
{% endtabs %}

## IO测试+测速

{% tabs test2,2 %}
<!-- tab 下载-->
```LINUX
wget -qO- https://raw.githubusercontent.com/oooldking/script/master/superbench.sh | bash
```
<!-- endtab -->

<!-- tab 功能预览-->
> 运行即执行

![功能预览](https://flie.pigax.cn/2022/09/07/6318465301fb4.jpg)
<!-- endtab -->

<!-- tab 项目地址-->
{% ghcard oooldking/script %}
<!-- endtab -->
{% endtabs %}

## 回程路由

{% tabs test2,2 %}
<!-- tab 下载-->
* 回程路由脚本一
```Linux
wget -qO- git.io/besttrace | bash
```
* 回程路由脚本二
```Linux
curl https://raw.githubusercontent.com/zhucaidan/mtr_trace/main/mtr_trace.sh|bash
```
<!-- endtab -->

<!-- tab 功能预览-->
> 运行即执行

* 回程路由脚本一
![功能预览](https://flie.pigax.cn/2022/09/07/6318467596416.jpg)
* 回程路由脚本二
![功能预览](https://flie.pigax.cn/2022/09/07/631846a54d466.jpg)

<!-- endtab -->

<!-- tab 项目地址-->
* 回程路由脚本一
{% ghcard zq/shell %}
* 回程路由脚本二
{% ghcard zhucaidan/mtr_trace %}
<!-- endtab -->
{% endtabs %}

# Linux应用类

## v2ray魔改版

{% tabs test2,2 %}
<!-- tab 下载-->
```Linux
wget --no-check-certificate https://raw.githubusercontent.com/jinwyp/one_click_script/master/trojan_v2ray_install.sh && chmod +x ./trojan_v2ray_install.sh && ./trojan_v2ray_install.sh
```
<!-- endtab -->

<!-- tab 功能预览-->
![功能预览](https://flie.pigax.cn/2022/09/07/631846ed2f70f.jpg)
<!-- endtab -->

<!-- tab 项目地址-->
{% ghcard jinwyp/one_click_script %}
<!-- endtab -->
{% endtabs %}

{% tip warning faa-horizontal animated faa-fast %}声明:本脚本只用于备份，不给予任何帮助{% endtip %}

## v2ray原版

{% tabs test2,2 %}
<!-- tab 下载-->
```Linux
bash <(curl -s -L https://git.io/v2rayinstall.sh)
```
<!-- endtab -->

<!-- tab 功能预览-->
![功能预览](https://flie.pigax.cn/2022/09/07/6318470889cc3.jpg)
<!-- endtab -->

<!-- tab 项目地址-->
{% ghcard xyz690/v2ray %}
<!-- endtab -->
{% endtabs %}

{% tip warning faa-horizontal animated faa-fast %}声明:本脚本只用于备份，不给予任何帮助{% endtip %}

## X-Ui

{% tabs test2,2 %}
<!-- tab 下载-->
```Linux
bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)
```
<!-- endtab -->

<!-- tab 功能预览-->
> 运行即执行

![功能预览](https://flie.pigax.cn/2022/09/07/63184723eeea6.jpg)
<!-- endtab -->

<!-- tab 项目地址-->
{% ghcard vaxilu/x-ui %}
<!-- endtab -->
{% endtabs %}

{% tip warning faa-horizontal animated faa-fast %}声明:本脚本只用于备份，不给予任何帮助{% endtip %}

## Docker

{% tabs test2,2 %}
<!-- tab 下载-->
```Linux
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh
```
<!-- endtab -->

<!-- tab 功能预览-->
> 运行即执行

![功能预览](https://flie.pigax.cn/2022/09/07/6318473ac5a74.jpg)
<!-- endtab -->

<!-- tab 项目地址-->
{% ghcard docker/docker-install %}
<!-- endtab -->
{% endtabs %}

## 宝塔COS挂载修复

{% tabs test2,2 %}
<!-- tab 下载-->
```Linux
wget -O cosfs.sh http://download.bt.cn/install/plugin/cosfs/install.sh && sh cosfs.sh instal
```
缺少依赖执行下面脚本
```Linux
yum install -y fuse-devel
```
<!-- endtab -->

<!-- tab 功能预览-->
> 运行即执行

![功能预览](https://flie.pigax.cn/2022/09/07/63184751d2b4e.jpg)
<!-- endtab -->

<!-- tab 项目地址-->
{% link BT, https://www.bt.cn/, https://bt.cn/Public/new/images/logo.svg %}
<!-- endtab -->
{% endtabs %}