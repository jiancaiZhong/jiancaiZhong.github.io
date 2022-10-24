---
layout: mypost
title: CentOs上部署安装Gitlab
categories: [CentOs, git, GitLab]
---

**安装环境**

```
centos版本:CentOS Linux release 7.9.2009 (Core)
gitlab版本:gitlab-ce-15.3.2-ce.0.el7.x86_64.rpm（ce:开源，el:CentOS）	
git版本：git version 1.8.3.1
```

**安装依赖**

```
yum install curl openssh-server openssh-clients postfix policycoreutils-python git
```

**启动ssh**

```
systemctl enable sshd
systemctl start sshd
```

**添加http服务到firewalld,pemmanent表示永久生效，若不加–permanent系统下次启动后就会失效**

```
systemctl start firewalld
firewall-cmd --permanent --add-service=http
systemctl reload firewalld
```

**启动postfix**（邮箱服务，本次安装没有启用，可以跳过这一步）

```
systemctl enable postfix
systemctl start postfix
```

**下载安装gitlab**

```
下载网址：https://mirrors.tuna.tsinghua.edu.cn/gitlab-ce/yum/el7（清华大学开源软件镜像站）

ce表示开源，el表示centos，el7对应CentOS 7
```

**选择GItLab版本**

![GitLab-select](GitLab_select.png)

**使用xftp将下载的文件上传到CentOs**

![xftp_upload_file](xftp_upload_file.png)

**上传GItLab安装包到CentOS**

![upload_GitLab_to_centOS](upload_GitLab_to_centOS.png)

**安装GitLab**

```
[root@localhost GitLab]# ls
gitlab-ce-15.3.2-ce.0.el7.x86_64.rpm
[root@localhost GitLab]# rpm -i gitlab-ce-15.3.2-ce.0.el7.x86_64.rpm 
warning: gitlab-ce-15.3.2-ce.0.el7.x86_64.rpm: Header V4 RSA/SHA1 Signature, key ID f27eab47: NOKEY
Preparing...                          ################################# [100%]
	package gitlab-ce-15.3.2-ce.0.el7.x86_64 is already installed
```

![install_GitLab](install_GitLab.png)

**修改端口号**

**进入到GitLab安装目录**

```
cd /opt/gitlab/etc
```

![GitLab_contents](GitLab_contents.png)

**备份GItLab配置文件**

```
[root@localhost etc]# ls
gitlab.rb.template
[root@localhost etc]# cp gitlab.rb.template gitlab.rb
[root@localhost etc]# ls
gitlab.rb  gitlab.rb.template
```

```
vim gitlab.rb

# 添加以下配置信息，修改端口号
external_url 'http://192.168.2.11'
gitlab_rails['gitlab_shell_ssh_port'] = 8099
```

**配置GitLab(配置完自动启动,默认账号root)**

```
# 使用gitlab-ctl命令 需要绝对路径
[root@localhost bin]# sudo /opt/gitlab/bin/gitlab-ctl reconfigure
```

**常用命令**

```
# 使用gitlab-ctl需要绝对路径
# 开启
sudo /opt/gitlab/bin/gitlab-ctl start
# 关闭
sudo /opt/gitlab/bin/gitlab-ctl stop
# 重启
sudo /opt/gitlab/bin/gitlab-ctl restart
# 帮助文档
sudo /opt/gitlab/bin/gitlab-ctl help
```

**界面访问**

```
# 不用端口号，上面配置的 external_url
http://192.168.2.11
```

**修改ip地址**（代码仓库的地址）

```
vim /opt/gitlab/embedded/service/gitlab-rails/config/gitlab.yml
# 修改localhost 为 git.farseersoft.com
```

![change_gitlab_ip](change_gitlab_ip.png)

**重启GitLab**（刷新不生效，则再次执行启动GitLab命令）

```
sudo /opt/gitlab/bin/gitlab-ctl restart
```

