---
layout: mypost
title: Kylin OS安装docker
categories: [Kylin, docker]
---

**查看版本号**

需要linux内核为3.1及以上

```bash
$  uname -r
3.10.0-693.el7.x86_64
```

**docker 离线安装包**（tgz格式） [点击下载 ](https://download.docker.com/linux/static/stable/x86_64/) 本次安装版本为 **docker-18.03.1-ce.tgz**

**解压docker安装包**

```bash
 $ tar -zxvf docker-18.03.1-ce.tgz
```

**复制到/usr/bin**

```bash
$ cp docker/* /usr/bin
```

> 上步中必须拷贝解压出的文件到/usr/bin目录下，而不是在/usr/bin下建立文件夹，然后再整个拷过来。否则，运行时报异常，应该是这个目录没有PATH中定义，所以不能在usr/bin下建立个docker目录，或者新建目录后到 /etc/profile 添加PATH。

**添加docker 服务**

```bash
# 新建 docker.service 文件
$ vim /etc/systemd/system/docker.service
```

这里是基础配置，详细配置可使用指定配置文件来启动服务

```bash
[Unit]
Description=Docker Application Container Engine 
Documentation=https://docs.docker.com
After=network-online.target firewalld.service
Wants=network-online.target

[Service] 
Type=notify

# the default is not to use systemd for cgroups because the delegate issues still
# exists and systemd currently does not support the cgroup feature set required 
# for containers run by docker
ExecStart=/usr/bin/dockerd
ExecReload=/bin/kill -s HUP $MAINPID

# Having non-zero Limit*s causes performance problems due to accounting overhead 
# in the kernel. We recommend using cgroups to do container-local accounting.
LimitNOFILE=infinity
LimitNPROC=infinity
LimitCORE=infinity 

# Uncomment TasksMax if your systemd version supports it. 
# Only systemd 226 and above support this version. 
#TasksMax=infinity 
TimeoutStartSec=0 

# set delegate yes so that systemd does not reset the cgroups of docker containers 
Delegate=yes

# kill only the docker process, not all processes in the cgroup 
KillMode=process 

# restart the docker process if it exits prematurely 
Restart=on-failure 
StartLimitBurst=3
StartLimitInterval=60s

[Install]
WantedBy=multi-user.target

```

**授权文件权限**

```bash
$ chmod +x /etc/systemd/system/docker.service
```

**重载unit配置文件**

```bash
$ systemctl daemon-reload 
```

**启动docker**

```bash
$ systemctl start docker
```

 **设置开机自启**

```bash
$ systemctl enable docker.service
```

**检查状态**

```bash
# 状态
systemctl status docker 

# 版本
docker -v
```

