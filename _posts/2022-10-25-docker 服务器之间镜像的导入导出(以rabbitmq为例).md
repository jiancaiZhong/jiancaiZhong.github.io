---
layout: mypost
title: docker 服务器之间镜像的导入导出
categories: [docker]
---

**服务器A 镜像导出**

​		查询服务器A所有镜像：docker images

**导出镜像**

```bash
$ docker save -o 导出文件名.tar 镜像名称（REPOSITORY）:镜像标签（TAG）
```

**例如：**

```bash
$ docker save -o rabbitmq.tar rabbitmq:3.9-management
```

![export_images.png](export_images.png)

**服务器B 镜像导入**

```bash
$ docker load -i 导入镜像名.tar 
```

**例如**

```bash
$ docker load -i rabbitmq.tar 
```

![import_images](import_images.png)

**运行rabbitmq**

**创建rabbitmq相应目录**

```bash
$ mkdir -p /data/docker-containers/rabbitmq
```

**运行**

```bash
# 进入rabbitmq相应目录
$ cd /data/docker-containers/rabbitmq

# 运行 （rabbitmq 密码： HG@783984535aL ）
$ docker run -d -p 5672:5672 -p 15672:15672 --hostname fsr-rabbit --name RabbitMQ -v `pwd`"/data":/var/lib/rabbitmq -e RABBITMQ_DEFAULT_VHOST=/ -e RABBITMQ_DEFAULT_USER=admin -e RABBITMQ_DEFAULT_PASS=HG@783984535aL rabbitmq:3.9-management
```

