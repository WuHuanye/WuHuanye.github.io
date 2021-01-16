---
title: 基于hexo搭建个人博客
date: 2020-10-19 11:36:33
categories: blog
tags: 
	- blog
	- hexo
comments: true
---


> 百金买骏马，千金买美人；万金买高爵，何处买青春？ —— 屈原
>
> <!--more-->

## 概述

1、 安装git	(因为git很早之前已安装，本文在这里就不说明了)

2、 安装nodejs

3、安装 hexo

4、正式搭建



## 安装nodejs

因为hexo依赖于nodejs，所以得先下载nodejs。下载地址：https://nodejs.org/en/  

{% asset_img nodejs.png This is an example image %}

下载下来是一个安装包，双击一路【next】默认即可（安装位置可自选）

## 安装hexo

在任意位置创建一个文件夹，自定义命名，这里以**blog**命名,在当前位置**(即blog的上一级目录)**鼠标右击选择**git bash here**,因为国内要直接下载安装 hexo 会很慢很慢，所以

- 输入一下命令安装 淘宝镜像

>  npm install -g cnpm --registry=https://registry.npm.taobao.org

- 安装成功后，输入命令开始安装**hexo**

> cnpm install -g hexo-cli

- 安装成功后，**初始化blog**

> hexo init blog  #这里的blog是你之前新建的文件夹名，比如你命名为test, 则这里的命令为 hexo init test

- 初始化完成后，进入blog文件夹，发现生成很多文件

  {% asset_img 博客目录结构.png This is an example image %}

> > node_modules:各依赖	source:源码 	themes:存放博客主题	_config.yml:博客配置文件

## 搭建

经过前面的几步，准备工作已完成。下面开始正式搭建及美化部署。

>1、cd blog 进入blog文件夹
>
>2、鼠标右键**gitbash here**,输入

```java
hexo s
```

该命令为启动服务命令，启动后，本地浏览器访问**localhost:4000**查看效果。

***

## 以github作为服务器将本地博客推至github上面

- 通过以上几个步骤已经实现了在本地浏览器访问博客，接下来说明如何推到远端并访问。

### 注册一个github账号http://github.com/

- 登录进入github中，创建仓库，即**new repostory**

{% asset_img 新建仓库.png This is an example image %}

- 复制该仓库的链接

{% asset_img 复制链接.png This is an example image %}

- 回到blog文件夹，打开_comfig.yml文件，编辑deploy下的这几个参数值，没有的自己加上，把**repo**的地址改为自己的

{% asset_img cofig编辑参数.png This is an example image %}

- 在blog文件夹下**gitbash here**,依次输入

> cnpm install hexo-deployer-git --save  #安装git部署插件
>
> hexo clean  #清理缓存，实际上是把public文件夹删除
>
> hexo g  #重新生成public文件夹
>
> hexo s  #启动服务，本地查看是否成功
>
> hexo d  # 将本地博客推至远程仓库中，推送完成之后浏览器访问**你的github用户名.github.io**查看效果

 