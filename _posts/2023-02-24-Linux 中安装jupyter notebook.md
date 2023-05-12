---
layout: mypost
title: Linux 中安装jupyter notebook
categories: [Linux]
---

> - Linux版本：`CentOS 3.10.0-1160.83.1.el7.x86_64`
> - Python版本：`Python 3.8.12`
> - Python安装路径：`/usr/local/bin/python3`

### 安装jupyter

所有操作在`root`权限下进行。安装`jupyter`之前，确保服务器中已安装好了python3

安装`jupyter`模块：

```shell
pip install jupyter
```

### 添加环境变量

把`jupyter`的安装路径添加到系统环境变量中

```sh
vi /etc/profile
export PATH=$PATH:/usr/local/bin/python3/bin/
```

保存后，重载配置文件

```sh
source /etc/profile
```

### 设置登录密码

安装`ipython`模块

```sh
pip install ipython
```

终端输入`ipython`进入`ipython`界面，输入以下进行密码设置：

```shell
from notebook.auth import passwd
passwd()
```

按照提示两次输入密码，次密码为之后登录`jupyter`的密码。同时，设置完成后，会自动生成一个hash串（sha1:xxxxx），复制下来，后面配置文件需要。

输入`exit()`退出`ipython`。

```shell
exit()
```

### 修改配置文件

终端输入命令：

```shell
jupyter-notebook --generate-config --allow-root
```

然后会生成配置文件，地址为：`/root/.jupyter/jupyter_notebook_config.py`

> 自己留意配置文件的位置

编辑配置文件，加入下面的内容：

```shell
# Nginx访问时会出现跨域访问，需要在这里允许
c.NotebookApp.allow_origin = '*'

# 禁止随意修改密码
c.NotebookApp.allow_password_change = False

# 是否允许远程访问
c.NotebookApp.allow_remote_access = True

# IP
c.NotebookApp.ip = '0.0.0.0'

# 端口
c.NotebookApp.port = 9820

# 工作目录
c.NotebookApp.notebook_dir = '/jupyter/'

# 启动Jupyter Notebook之后是否打开浏览器
c.NotebookApp.open_browser = False

# 客户端打开Jupyter Notebook的密码哈希值
c.NotebookApp.password = '上面输入两次密码后生成的哈希字符串'
```

> - ip设置为0.0.0.0，可以保证局域网内其他用户访问；
> 
> - 端口设置为9820，默认为8888，也可以为其他，但要保证不会发生端口占用；
> 
> - 工作目录自定义设置，含义为jupyter noteboo启动时的默认工作目录，不存在则手动创建，再来启动；
> 
> - 密码哈希值为设置登录密码时自动生成的。

### 项目启动

#### 前台启动

```shell
jupyter-notebook --allow-root
```

#### 后台启动

```shell
nohup jupyter notebook --allow-root > /jupyter/jupyter.log 2>&1 &
```

1. `nohup` 表示no hang up，不挂起，命令执行后即使终端退出，服务也不会停止。
2. 并指定日志文件路径为`/jupyter/jupyter.log`。

以上两种方式任选其一，运行`jupyter`服务，然后在浏览器通过ip+port的形式访问`jupyter notebook`。输入设置的密码，登录即可。
