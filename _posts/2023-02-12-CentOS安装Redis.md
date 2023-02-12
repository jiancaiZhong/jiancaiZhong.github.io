---
layout: mypost
title: CentOS 安装 Redis
categories: [Linux]
---

> 本次安装目录在 `/usr/local/redis` 中，安装文件也下载在这里

#### 一、下载

进入安装目录 `/usr/local/redis ` 中进行下载源码：

```shell
$ wget http://download.redis.io/releases/redis-4.0.2.tar.gz
```

#### 二、解压

```shell
$ tar -zxvf redis-4.0.2.tar.gz 
```

#### 三、进入解压目录

```shell
$ cd redis-4.0.2
```

#### 四、编译安装

```shell
$ make
$ make install
```

#### 五、修改配置

进入到redis源码文件夹`/usr/local/redis/redis-4.0.2`

```shell
$ /usr/local/redis/redis-4.0.2
$ vim redis.conf
```

##### 5.1、后台启动

```
把daemonize no 替换成 daemonize yes
```

##### 5.2、监听ip

注释掉监听ip，则监听所有ip

```shell
# bind 127.0.0.1
```

#### 六、启动

启动文件在`/usr/local/bin`，使用命令`cd /usr/local/bin` 进入到该文件夹下运行 `redis-server` 则可以启动**redis**，此时是非后台进程启动，后台进程启动命令：

```shell
$ ./redis-server &
```

#### 七、配置文件参数说明

```text
daemonize：如需要在后台运行，把该项的值改为yes
 
pdifile：把pid文件放在/var/run/redis.pid，可以配置到其他地址
 
bind：指定redis只接收来自该IP的请求，如果不设置，那么将处理所有请求，在生产环节中最好设置该项
 
port：监听端口，默认为6379
 
timeout：设置客户端连接时的超时时间，单位为秒
 
loglevel：等级分为4级，debug，revbose，notice和warning。生产环境下一般开启notice
 
logfile：配置log文件地址，默认使用标准输出，即打印在命令行终端的端口上
 
database：设置数据库的个数，默认使用的数据库是0
 
save：设置redis进行数据库镜像的频率
 
rdbcompression：在进行镜像备份时，是否进行压缩
 
dbfilename：镜像备份文件的文件名
 
dir：数据库镜像备份的文件放置的路径
 
slaveof：设置该数据库为其他数据库的从数据库
 
masterauth：当主数据库连接需要密码验证时，在这里设定
 
requirepass：设置客户端连接后进行任何其他指定前需要使用的密码
 
maxclients：限制同时连接的客户端数量
 
maxmemory：设置redis能够使用的最大内存
 
appendonly：开启appendonly模式后，redis会把每一次所接收到的写操作都追加到appendonly.aof文件中，当redis重新启动时，会从该文件恢复出之前的状态
 
appendfsync：设置appendonly.aof文件进行同步的频率
 
vm_enabled：是否开启虚拟内存支持
 
vm_swap_file：设置虚拟内存的交换文件的路径
 
vm_max_momery：设置开启虚拟内存后，redis将使用的最大物理内存的大小，默认为0
 
vm_page_size：设置虚拟内存页的大小
 
vm_pages：设置交换文件的总的page数量
 
vm_max_thrrads：设置vm IO同时使用的线程数量
```
