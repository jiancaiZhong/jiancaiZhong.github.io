---
layout: mypost
title: macOS安装 WeChatTweak-macOS
categories: [macOS,WeChat]
---

**首次使用**安装 WeChatTweak-CLI:

```bash
$ brew install sunnyyoung/repo/wechattweak-cli
```

**安装过程：**

```bash
➜  ~ brew install sunnyyoung/repo/wechattweak-cli
==> Tapping sunnyyoung/repo
Cloning into '/usr/local/Homebrew/Library/Taps/sunnyyoung/homebrew-repo'...
remote: Enumerating objects: 69, done.
remote: Counting objects: 100% (69/69), done.
remote: Compressing objects: 100% (49/49), done.
remote: Total 69 (delta 25), reused 62 (delta 18), pack-reused 0
Unpacking objects: 100% (69/69), done.
Tapped 3 casks (84 files, 30.7KB).
==> Downloading https://github.com/Sunnyyoung/WeChatTweak-CLI/releases/download/1.4/wechattweak-cli
==> Downloading from https://objects.githubusercontent.com/github-production-release-asset-2e65be/40
######################################################################## 100.0%
==> Installing Cask wechattweak-cli
==> Linking Binary 'wechattweak-cli' to '/usr/local/bin/wechattweak-cli'
🍺  wechattweak-cli was successfully installed!
```

**进入安装文件夹：**

```bash
$ cd /usr/local/bin/
```

**安装/更新Tweak:**

```bash
$ sudo wechattweak-cli install
```

**卸载Tweak：**

```bash
$ sudo wechattweak-cli uninstall
```

