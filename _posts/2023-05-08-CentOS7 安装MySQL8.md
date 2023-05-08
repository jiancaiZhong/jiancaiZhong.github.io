---
layout: mypost
title: CentOS7 安装 MySQL8
categories: [Linux,MySQL]
---

> 宿主机版本号 CentOS 3.10.0-1160.83.1.el7.x86_64
> MySQL版本：MySQL8

### 安装MySQL8

#### 在 root 目录下，安装 `mysql` 和 `mysql-devel`

```sh
yum install mysql
yum install mysql-devel
```

#### 安装 mysql-server

```sh
wget http://dev.mysql.com/get/mysql80-community-release-el7-5.noarch.rpm
rpm -ivh mysql80-community-release-el7-5.noarch.rpm
yum install mysql-community-server
```

#### 安装成功后重启`mysql`服务

```sh
service mysqld restart
```

#### 查看密码

```sh
cat /var/log/mysqld.log | grep password
```

> 记住上面查询的密码，待会登录需要用到

#### 设置密码

```sh
# 登录mysql并输入密码
mysql -u root -p

# mysql8 修改密码方式
alter user 'root'@'localhost' identified by '这里填你要的密码';
```

> - 修改密码时，需要 **符合长度，且含有数字、小写或大写字母、特殊字符**
> - 无需重启数据库即可生效（且`mariadb`自动会被替换，不再生效）

#### 配置远程连接授权设置（改表法）

```mysql
use mysql;
update user  set host = '%' where user = 'root';
select host,  user from user;
```
