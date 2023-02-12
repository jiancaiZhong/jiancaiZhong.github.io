---
layout: mypost
title: CentOS 升级 git 版本
categories: [Linux]
---

> CentOS 自带的 git 版本是1.x的，但是我们需要用到的git版本经常都是2.x的，我在升级过程中踩过很多坑，现在写一篇博客记录一下，防止大家踩坑
>
> 本次升级宿主机版本号 CentOS 3.10.0-1160.83.1.el7.x86_64

### 移除旧版本

```shell
sudo yum remove git

sudo yum remove git-*
```

### 编译安装

#### 安装依赖

```shell
sudo yum install curl-devel expat-devel gettext-devel openssl-devel zlib-devel

sudo yum install gcc perl-ExtUtils-MakeMaker
```

#### 下载源码

[**git** 项目地址](https://github.com/git/git)

下载链接（以v2.34.1为例）： https://github.com/git/git/archive/v2.34.1.tar.gz

需要其他版本，请进入 [git项目地址](https://github.com/git/git) 获取版本号，版本号获取方式如下：

![](20230212155131.png)

此时将下载链接的版本号换成你想要的版本号，进行源码的下载即可。

#### 解压安装git

将你下载的源码（以v2.34.1为例）上传到CentOS，进入到源码目录下。将源码进行解压

```shell
tar -xvf v2.34.1.tar.gz

rm -f v2.34.1.tar.gz

cd git-2.34.1
```

然后编译安装：

```shell
make configure

sudo ./configure --prefix=/usr

sudo make

sudo make install
```

安装完成之后，检查 `git` 版本：

```shell
git --version
```

此时就完成了，升级过程有问题，需要帮助可以[email](mailto:zhong@jiancai.email) 我。
