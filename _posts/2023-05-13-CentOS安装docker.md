---
layout: mypost
title: CentOS安装docker
categories: [Linux,docker]
---

> 参考 [菜鸟教程](https://www.runoob.com/docker/centos-docker-install.html) 采取手动安装的方式安装 `docker`

### 卸载旧版本

```bash
$ sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
```

### 使用 Docker 仓库进行安装

在新主机上首次安装 `Docker Engine-Community` 之前，需要设置 `Docker` 仓库。之后，您可以从仓库安装和更新 `Docker`。

**设置仓库**

安装所需的软件包。`yum-utils` 提供了 `yum-config-manager` ，并且 `device mapper` 存储驱动程序需要 `device-mapper-persistent-data` 和 `lvm2`。

```bash
$ sudo yum install -y yum-utils \
  device-mapper-persistent-data \
  lvm2
```

使用以下命令来设置稳定的仓库

**使用官方源地址（比较慢）**

```bash
$ sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
```

**阿里云**

```bash
$ sudo yum-config-manager \
    --add-repo \
    http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
```

**清华大学源**

```bash
$ sudo yum-config-manager \
    --add-repo \
    https://mirrors.tuna.tsinghua.edu.cn/docker-ce/linux/centos/docker-ce.repo
```

**安装最新版本的 `Docker Engine-Community` 和 `containerd`**

```bash
$ sudo yum install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

**安装特定版本的 `Docker Engine-Community`**

1.列出并排序您存储库中可用的版本。此示例按版本号（从高到低）对结果进行排序。

```bash
$ yum list docker-ce --showduplicates | sort -r

docker-ce.x86_64  3:18.09.1-3.el7                     docker-ce-stable
docker-ce.x86_64  3:18.09.0-3.el7                     docker-ce-stable
docker-ce.x86_64  18.06.1.ce-3.el7                    docker-ce-stable
docker-ce.x86_64  18.06.0.ce-3.el7                    docker-ce-stable
```

2.通过其完整的软件包名称安装特定版本，该软件包名称是软件包名称（`docker-ce`）加上版本字符串（第二列），从第一个冒号（:）一直到第一个连字符，并用连字符（-）分隔。例如：`docker-ce-18.09.1`。

```bash
$ sudo yum install docker-ce-<VERSION_STRING> docker-ce-cli-<VERSION_STRING> containerd.io
```

3.启动 Docker

```bash
$ sudo systemctl start docker
```

4.通过运行 hello-world 镜像来验证是否正确安装了 Docker Engine-Community 。

```bash
$ sudo docker run hello-world
```

### 设置开机启动

```bash
systemctl enable docker
```
