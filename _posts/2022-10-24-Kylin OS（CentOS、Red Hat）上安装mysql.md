---
layout: mypost
title: Kylin OS（CentOS、Red Hat）上安装mysql
categories: [Kylin, mysql]
---

> Kylin OS和Red Hat、CentOS 基本通用

- **Kylin OS版本**

  ```bash
  Linux i-417EBD09 3.10.0-693.el7.x86_64 #1 SMP Thu Sep 14 15:11:35 CST 2017 x86_64 x86_64 x86_64 GNU/Linux
  ```

  el7 :选择安装包时候注意 

- **rpm安装包下载**

下载红帽的mysql 5.7.38 rpm安装包 [下载地址](https://downloads.mysql.com/archives/community/)

选择对应版本：（本次选择**Red Hat Enterprise Linux 7 / Oracle Linux 7 (x86, 64-bit), RPM Bundle**）

![select_mysql_version](select_mysql_version.png)

- **上传安装包到服务器并解压**

  1. **上传**

     使用xftp或者其他工具上传

  2. **解压**

     ```bash
     $ tar -xvf mysql-5.7.38-1.el7.x86_64.rpm-bundle.tar 
     ```

![mysql_rpm_list](mysql_rpm_list.png)

- **删除系统自带mariadb**（不删除会影响后面安装mysql-client）
  
  - **检查是否自带mariadb数据库**
  
    ```bash
    $ rpm -qa|grep mariadb
    ```
  如果有，则返回给你一个标志，反之则没有返回。
  
  - **删除mariadb数据库**
  
    ```bash
     $ rpm -e --nodeps mariadb-5.5.56-2.el7.x86_64
    ```
  
    ![del_mariadb](del_mariadb.png)

- **安装MySql**（注意：你一定要按照common->libs->client->server顺序进行安装，因为rpm包之间相互依赖。）

  ```bash
  $ rpm -ivh mysql-community-common-5.7.38-1.el7.x86_64.rpm
  $ rpm -ivh mysql-community-libs-5.7.38-1.el7.x86_64.rpm
  $ rpm -ivh mysql-community-client-5.7.38-1.el7.x86_64.rpm 
  $ rpm -ivh mysql-community-server-5.7.38-1.el7.x86_64.rpm
  ```

  ![install_mysql](install_mysql.png)

- **确认是否成功安装了4个rpm包**

    ```bash
    $ rpm -qa | grep mysql
    ```
    
    ![is-install_mysql](is-install_mysql.png)

- **启动mysql**

  - **查看mysql版本**

    ```bash
    $ mysql --version
    ```

  - **跳过权限登录**

    ```bash
    $ vim /etc/my.cnf
    
    # 添加以下配置信息
    [mysqld]
    skip-grant-tables
    ```

    ![skin-root](skin-root.png)
    
  - **启动mysql服务**
  
    ```bash
    $ service mysqld restart
    ```
  
  - **登录mysql，直接回车不用密码**（也可以使用临时密码）
  
    查看临时密码： cat /var/log/mysqld.log（最后一行）
  
    ![login-mysql](login-mysql.png)
  
  - **修改临时密码**（Gzlry@6789923Hk）
  
    ```mysql
    mysql> use mysql;
    mysql> update user set authentication_string = password('newPassword'), password_expired = 'N', password_last_changed = now() where user = 'root';
    mysql> exit (退出mysql之后，关掉跳过权限，并且重启mysql服务)
    ```
  
    ![open-root](open-root.png)
  
  - **允许mysql远程连接**
  
    ```mysql
    mysql> use mysql;
    mysql> select user,host from user;
    +---------------+-----------+
    | user          | host      |
    +---------------+-----------+
    | root          | localhost |
    | mysql.session | localhost |
    | mysql.sys     | localhost |
    +---------------+-----------+
    -- 设置root用户允许远程连接
    mysql> update user set host = '%' where user = 'root';
    -- 立即生效
    mysql> flush privileges;
    ```
  
  - **设置mysql开机启动**
  
    ```bash
     $ vim /etc/rc.d/rc.local
     # 添加mysql启动命令
     $ service mysqld start
    ```
