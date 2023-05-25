---
layout: mypost
title: CentOS安装nginx（官网）
categories: [Linux,nginx]
---

> 本次安装方法是从[官网]([nginx: Linux packages](http://nginx.org/en/linux_packages.html#RHEL))搬运的

### 安装依赖

```bash
sudo yum install yum-utils
```

设置 `yum` 源

```bash
# 新建文件
vim /etc/yum.repos.d/nginx.repo

# 输入一下内容
[nginx-stable]
name=nginx stable repo
baseurl=http://nginx.org/packages/centos/$releasever/$basearch/
gpgcheck=1
enabled=1
gpgkey=https://nginx.org/keys/nginx_signing.key
module_hotfixes=true

[nginx-mainline]
name=nginx mainline repo
baseurl=http://nginx.org/packages/mainline/centos/$releasever/$basearch/
gpgcheck=1
enabled=0
gpgkey=https://nginx.org/keys/nginx_signing.key
module_hotfixes=true
```

默认情况下，使用稳定 nginx 包的存储库。如果您想使用主线 nginx 包，请运行以下命令：

```bash
sudo yum-config-manager --enable nginx-mainline
```

### 安装 `nginx`

```bash
sudo yum install nginx
```

### 开机启动

```bash
systemctl enable nginx
```

### 常用命令

```bash
service nginx start # 启动
service nginx restart # 重启
service nginx stop # 停止
service nginx status # 查看状态
nginx -t # 测试配置文件的正确性
nginx -s stop # 立即停止
nginx -s quit # 平滑停止，不允许新的进程，所有进程结束后再退出
nginx -s reload # 平滑重启服务
```
