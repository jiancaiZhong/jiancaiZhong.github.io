---
layout: mypost
title: windows下MySQL 5.7+ 解压缩版安装配置
categories: [MySQL]
---

**[MySQL 官网](https://dev.mysql.com/downloads/mysql/)** 下载中心

**安装**

1. **解压至你想要的位置**
2. **在解压的MySQL根目录下用记事本新建文件my.ini文件，字符集为：ANSI**

> **注意**
>
> - 设置mysql的安装目录
>
> - 设置mysql数据库的数据的存放目录

```
[mysql]
# 设置mysql客户端默认字符集
default-character-set=utf8 
[mysqld]
#设置3306端口
port = 3306 
# 设置mysql的安装目录
basedir=D:\Program Files\mysql-5.7.31-winx64
# 设置mysql数据库的数据的存放目录
datadir=D:\Program Files\mysql-5.7.31-winx64\data
# 允许最大连接数
max_connections=200
# 服务端使用的字符集默认为8比特编码的latin1字符集
character-set-server=utf8
# 创建新表时将使用的默认存储引擎
default-storage-engine=INNODB
#开启查询缓存
explicit_defaults_for_timestamp=true
#设置MySQL5.7兼容低版本MySQL的类型
sql-mode=STRICT_TRANS_TABLES,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER
```

my.ini的文件路径如下图所示

 ![1604548889.png](1604548903141041002.png)

3. **初始化数据库**

（1）以管理员身份运行cmd，并cd到mysql中的bin目录下，执行命令：

```bash
mysqld --initialize --user=mysql --console
```

注意：如果执行出现如下报错信息，请下载应用程序所需要的组件，[点击下载](https://www.microsoft.com/zh-CN/download/details.aspx?id=40784)

![1BKL3XWOER)VO2YL.png](1594213836083054299.png)

（2）该命令会创建data目录与数据库，生成**root用户和临时密码**，我们需要记住这个命令以便于登录。

4. **配置环境变量**

右键此电脑（计算机）-属性-高级系统设置-高级-环境变量，在系统变量中的PATH中加入你的bin目录，如：D:\Program Files\mysql-5.7.26-winx64\bin，点确定！一般不需要重启。

5. **安装MySQL服务**

以管理员身份运行cmd，并输入下面的命令执行。

```bash
# 默认安装
mysqld install

# 指定配置文件位置安装(Win server 2008需要指定)
mysqld --install MySQL --defaults-file=D:\Program Files\mysql-5.7.26-winx64\my.ini
```

6. **启动服务**

在终端，输入`net start mysql`启动MySQL服务，再输入`mysql -u root -p`，然后输入临时密码，然后设置新密码。

7. **修改密码**

设置密码方法有两个，推荐第一个
方法一：

```mysql
alter user 'root'@'localhost' identified by 'password';
```

方法二：

```mysql
update mysql.user set authentication_string=PASSWORD('password') where User='root';
```

Linux（skip-grant-tables=1）：

```mysql
update user set authentication_string = password('password'), password_expired = 'N', password_last_changed = now() where user = 'root';
```

可能无效的方法：

```mysql
update user set password = PASSWORD('password') where user = 'root';
```
