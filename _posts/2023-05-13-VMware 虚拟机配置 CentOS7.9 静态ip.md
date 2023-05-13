---
layout: mypost
title: VMware 虚拟机配置 CentOS7.9 静态ip
categories: [Linux,VMware]
---

> - VMware版本：VMware® Workstation 17 Pro 
> 
> - CentOS版本：CentOS7.9

### 1.CentOS虚拟机网络设置

打开VMware，在我的计算机下选中要配置的CentOS虚拟机，点击 `编辑虚拟机设置`，将虚拟机网络设置成 `NAT模式(N):用于共享主机的IP地址`

![](Snipaste_2023-05-13_17-29-09.png)

### 2.修改 VMware 虚拟网络编辑器

打开 `vmware`，依次点击顶部的 `编辑`、`虚拟网络编辑器`，选中第三个选项 `VMnet8`

![](Snipaste_2023-05-13_17-34-20.png)

把 `使用本地DHCP服务将 IP地址分配给虚拟机`  的勾去掉，目的是禁止 动态给 `CentOS` 虚拟机分配IP地址，其它地方不用修改。

### 3.记录VMware的网关IP地址

点击上图的 `NAT设置` 获取网关 `ip` 待会在虚拟机钟配置 `静态IP` 需要用到

![](Snipaste_2023-05-13_17-38-55.png)

### 4.VMware网络适配器设置

依次进入 `控制面板`、`网络和 Internet` 、`更改适配器设置`，右键 `VMware Network Adapter VMnet8`、`属性`，然后选择 `Internet协议版本4(TCP/Ipv4)` 选项,点击 `属性`

![](Snipaste_2023-05-13_17-43-46.png)

注意这里的IP `192.168.10.1` 不能和上面的VMware的网关IP `192.168.10.2` 产生冲突，否则会导致找不到真正的VMware虚拟机网关

### 5.修改centos网络服务配置文件

使用 `ip add` 命令查看网卡名称

![](Snipaste_2023-05-13_17-52-26.png)

可以看出网卡名称为 `ens33`

修改网络配置文件 `vim /etc/sysconfig/network-scripts/ifcfg-ens33` 

修改前

```bash
TYPE="Ethernet"
PROXY_METHOD="none"
BROWSER_ONLY="no"
BOOTPROTO="dhcp"
DEFROUTE="yes"
IPV4_FAILURE_FATAL="no"
IPV6INIT="yes"
IPV6_AUTOCONF="yes"
IPV6_DEFROUTE="yes"
IPV6_FAILURE_FATAL="no"
IPV6_ADDR_GEN_MODE="stable-privacy"
NAME="ens33"
UUID="56e58af4-fbce-4a12-a13b-5efa0f4d30d5"
DEVICE="ens33"
ONBOOT="yes"
```

修改后

```bash
TYPE="Ethernet"
PROXY_METHOD="none"
BROWSER_ONLY="no"
BOOTPROTO="statis"
DEFROUTE="yes"
IPV4_FAILURE_FATAL="no"
IPV6INIT="yes"
IPV6_AUTOCONF="yes"
IPV6_DEFROUTE="yes"
IPV6_FAILURE_FATAL="no"
IPV6_ADDR_GEN_MODE="stable-privacy"
NAME="ens33"
UUID="56e58af4-fbce-4a12-a13b-5efa0f4d30d5"
DEVICE="ens33"
ONBOOT="yes" # 开机激活网卡
DNS1=114.114.114.114 # 国内固定
IPADDR=192.168.10.11 # 配置的静态IP
NETMASK=255.255.255.0 # 子网掩码
GATEWAY=192.168.10.2 # 网关IP，这里是VMware网关IP地址
```

注意设置的静态IP只要不是 `192.168.10.1` 和 `192.168.10.2` 且前三个网段一样理论上

`192.168.10.3` ——`192.168.10.253` 都可以，`service network restart` 命令重启网络，再用 `ifconfig` 查看IP

![](Snipaste_2023-05-13_18-06-05.png)

 配置结束，尽情享用静态IP带来的快乐吧
