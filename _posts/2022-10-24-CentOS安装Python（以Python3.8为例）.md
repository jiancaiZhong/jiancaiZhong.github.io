---
layout: mypost
title: CentOS安装Python（以Python3.8为例）
categories: [CentOS, Python]
---


### CentOS安装部署Python3.8

1. #### 查看linux系统版本

   ```bash
   $ cat /etc/centos-release
   CentOS Linux release 7.9.2009 (Core)
    
   $ uname -a
   Linux localhost.localdomain 3.10.0-1160.el7.x86_64 #1 SMP Mon Oct 19 16:18:59 UTC 2020 x86_64 x86_64 x86_64 GNU/Linux
    
   $ python -V
   Python 2.7.5 # 系统默认安装了Python 2.7.5
   ```

2. #### 安装依赖

   ```bash
   $ yum install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gcc make libffi-devel
   ```

3. #### 下载python源码包

   下载python 3.8 稳定版

   ```bash
   $ wget https://www.python.org/ftp/python/3.8.12/Python-3.8.12.tgz
   ```

4. #### 解压并安装python

   ```bash
   # 解压
   $ tar -zxvf Python-3.8.12.tgz
    
   #编译
   $ cd Python-3.8.12/
   $ ./configure
   $ make
    
   # 安装
   $ make install
    
   # 建立命令软链接
   $ which python
   /usr/bin/python # 可以看到默认的python路径为/usr/bin/python
    
   $ which python3
   /usr/local/bin/python3 # python3的路径为/usr/local/bin/python3
    
   # 将python3的软链接加到python上
   $ mv /usr/bin/python /usr/bin/python.bak
   $ ln -s /usr/local/bin/python3 /usr/bin/python
    
   # 查看默认python版本
   $ python -V # 这时python的版本已经是3.8.12了
   Python 3.8.12
    
   # 软连接pip 命令到pip3
   $ which pip3
   /usr/local/bin/pip3
    
   $ ln -s /usr/local/bin/pip3 /usr/bin/pip
    
   # 查询pip3 版本
   $ pip -V
   pip 21.1.1 from /usr/local/lib/python3.8/site-packages/pip (python 3.8)
   ```

   

5. #### 配置yum

   > yum是依赖python2.7的，改完软链接以后,python改成了3.8了，所以yum会报错

   ```bash
   # 将以下两个文件的第一行 #!/usr/bin/python 修改为python 2.7.5的路径 ———》 #!/usr/bin/python2.7 或者 #!/usr/bin/python2
   $ vim  /usr/libexec/urlgrabber-ext-down
   $ vim  /usr/bin/yum
   ```
   
   