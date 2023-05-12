---
layout: mypost
title: CentOS 安装 oh-my-zsh
categories: [Linux]
---

> **zsh**也是一种 **shell**，兼容最常用的 **bash** 这种 **shell** 的命令和操作，**bash** 虽然很标准，但是自己日常使用方便更重要。**oh-my-zsh** 提供了丰富的插件
> 
> 宿主机版本号 CentOS 3.10.0-1160.83.1.el7.x86_64

### 安装

先使用命令 `cat /etc/shells` 查看系统支持的 shell ,正常情况下是这样的

```shell
root@localhost ~                                                                                                                 
> # cat /etc/shells                                                                                                             
/bin/sh
/bin/bash
/usr/bin/sh
/usr/bin/bash
/bin/tcsh
/bin/csh
```

> 安装 **oh-my-zsh** 需要先安装 `zsh` , 如果没有就使用命令 `sudo yum install -y zsh` 安装 `zsh`

### 官网安装

> [官网](https://ohmyz.sh/#install)

安装方法：直接运行以下脚本

```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

注意：国内有时候不成功，因为安装脚本的服务器在国外，现在我将下载好的脚本放在这里供大家下载

点击 [oh-my-zsh](install.sh) 下载安装脚本

### 离线安装

将刚才的脚本下载好以后放到你的CentOS系统下，进入安装脚本目录，使用命令 `chmod u+x install.sh` 给安装脚本执行权限，然后使用命令 `sh install.sh` 执行脚本，此时系统会自动执行安装程序。

### 切换shell

再次使用命令 `cat /etc/shells` 查看系统支持的 shell ,会多了以下内容

```shell
root@localhost ~                                                                                                                 
> # cat /etc/shells                                                                                                             
...
/bin/zsh
```

使用命令 `chsh -s /bin/zsh` 切换 **shell**

### 插件安装

**oh-my-zsh** 中有内置有很多插件,使用命令 `vim ~/.zshrc` 打开,找到 **plugins**

```sh
plugins=(
   git
   extract
   z
   zsh-syntax-highlighting
   zsh-autosuggestions
 )
```

**extract** ：用于解压任何压缩文件，不必根据压缩文件的后缀名来记忆压缩软件
**z** ：可以直接跳转到曾经去过的文件夹

**zsh-syntax-highlighting** 和 **zsh-autosuggestions** 这两个插件强烈推荐，一个是高亮，一个是自动补全，Linux系统很需要这两个功能吧？

两个插件的安装方法：

将项目克隆到` ~/.oh-my-zsh/plugins/`中,然后再`~/.zshrc`中的 plugins 中加上 **zsh-syntax-highlighting** 和 **zsh-autosuggestions** 即可

**注意：**  **oh-my-zsh** 所有插件都放在 **~/.oh-my-zsh/plugins/** 中

```shell
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/plugins/zsh-syntax-highlighting
```

项目在 **GitHub** ，访问失败的话建议使用代理或者手动下载后将文件放在插件目录手动添加，最后需要其他的插件请自行访问[官网](https://ohmyz.sh/#install)安装

### 主题

**oh-my-zsh** 的配置文件在 **~/.zshrc**，使用命令`vim ~/.zshrc` 修改 **ZSH_THEME="bureau"**，其中 **bureau** 为主题，还有很多主题请自行百度，在 **GitHub**上可以预览 [oh-my-zsh 主题](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)
