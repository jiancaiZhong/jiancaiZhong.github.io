---
layout: mypost
title: windows 以管理员模式运行 bat 脚本
categories: [Windows]
---

> 本文解决**windows**运行**bat**脚本时候需要提示管理员运行

在**bat**脚本添加：

```bash
@ECHO OFF
setlocal EnableDelayedExpansion
PUSHD %~DP0 & cd /d "%~dp0"
%1 %2
mshta vbscript:createobject("shell.application").shellexecute("%~s0","goto :runas","","runas",1)(window.close)&goto :eof
:runas
```

