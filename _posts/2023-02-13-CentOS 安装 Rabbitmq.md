---
layout: mypost
title: CentOS 安装 rabbitmq
categories: [Linux]
---

> 宿主机版本号 CentOS 3.10.0-1160.83.1.el7.x86_64
> 
> 由于rabbitmq是基于erlang语言开发的，所以必须先安装erlang

### 一、安装依赖

```shell
$ yum -y install gcc glibc-devel make ncurses-devel openssl-devel xmlto perl wget gtk2-devel binutils-devel
```

### 二、下载erlang

```shell
$ wget https://ghproxy.com/github.com/erlang/otp/releases/download/OTP-24.2.1/otp_src_24.2.1.tar.gz
```

注意：如果下在慢可以使用代理或者windows下载后上传到CentOS

### 三、安装erlang

```shell
$ tar -zxvf /root/opt_src_24.2.1.tar.gz
$ mv otp_src_24.2.1 /usr/local/
$ cd /usr/local/otp_src_24.2.1/
$ mkdir ../erlang/
$ ./configure --prefix=/usr/local/erlang
$ make install
$ echo 'export PATH=$PATH:/usr/local/erlang/bin' >> /etc/profile
$ source /etc/profile
```

注意：中间可能会出现相关警告，直接忽略即可

### 四、下载rabbitmq

```shell
$ wget https://ghproxy.com/github.com/rabbitmq/rabbitmq-server/releases/download/v3.9.13/rabbitmq-server-generic-unix-3.9.13.tar.xz
```

注意：如果下在慢可以使用代理或者windows下载后上传到CentOS

### 五、安装rabbitmq

```shell
$ yum install -y xz
$ xz -d rabbitmq-server-generic-unix-3.9.13.tar.xz 
$ tar -xvf rabbitmq-server-generic-unix-3.9.13.tar 
$ mv rabbitmq_server-3.9.13/ /usr/local/
$ cd /usr/local/
$ mv rabbitmq_server-3.9.13/ rabbitmq
$ echo 'export PATH=$PATH:/usr/local/rabbitmq/sbin' >> /etc/profile
$ source /etc/profile
```

### 六、配置rabbitmq

#### 6.1 启动

```shell
$ rabbitmq-server -detached
```

#### 6.2 状态检查

```shell
$ rabbitmq-server -status
```

#### 6.3 开启webui

```shell
$ rabbitmq-plugins enable rabbitmq_management
```

#### 6.4 访问

```
localhost:15672
```

#### 6.5 设置用户

```shell
$ rabbitmqctl add_user username password
```

#### 6.6 设置管理员

```shell
$ rabbitmqctl set_user_tags username administrator
```

#### 6.7 设置权限

```shell
$ rabbitmqctl set_permissions -p / username ".*" ".*" ".*"
```
