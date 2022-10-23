---
layout: mypost
title: windows 定时执行重启sql service 使用文档
categories: [Schtasks]
---

**[sql-service 重启脚本](sql-service 重启脚本.zip)**

### 脚本参数说明

- **create-restart-msqlservicetask.bat**（创建定时任务）

**关键脚本命令**

```bash
SCHTASKS /Create /tn restartSqlService-excute-everyday /sc daily /st 01:00:00  /tr C:\Users\Administrator\Desktop\sql-service-restart.bat
```
**完整脚本**

```bash
# 以管理员身份终端打开执行
@ECHO OFF

setlocal EnableDelayedExpansion

color 3e #终端颜色

title Restart Sql Service # 打开的终端标题

PUSHD %~DP0 & cd /d "%~dp0"

%1 %2

mshta vbscript:createobject("shell.application").shellexecute("%~s0","goto :runas","","runas",1)(window.close)&goto :eof

:runas

# 以上代码为声明在管理员模式下打开
# 以下为需要执行的命令

SCHTASKS /Create /tn restartSqlService-excute-everyday /sc daily /st 01:00:00  /tr C:\Users\Administrator\Desktop\sql-service-restart.bat

# 执行完命令后暂停，点按任意按键退出（可以删除 pause >nul 进行 跳过这一步）
pause >nul

exit
```

**参数说明**

```bash
/tn 任务名

/sc 运行频率

/st 运行时间

/tr 定时任务需要执行的脚本路径
```

- **sql-service-restart.bat**（重启sql service）

**关键脚本命令**

```bash
net stop MSSQL$SQLEXPRESS

net start MSSQL$SQLEXPRESS
```

**完整脚本**

```bash
# 以管理员身份终端打开执行
@ECHO OFF

setlocal EnableDelayedExpansion

color 3e #终端颜色

title Restart Sql Service # 打开的终端标题

PUSHD %~DP0 & cd /d "%~dp0"

%1 %2

mshta vbscript:createobject("shell.application").shellexecute("%~s0","goto :runas","","runas",1)(window.close)&goto :eof

:runas

# 以上代码为声明在管理员模式下打开
# 以下为需要执行的命令
  
echo restart sqlService ...!

net stop MSSQL$SQLEXPRESS

echo stop sqlService success!

net start MSSQL$SQLEXPRESS

echo restart sqlService success!
echo After execution, any key will exit!

# 执行完命令后暂停，点按任意按键退出（可以删除 pause >nul 进行 跳过这一步）
pause >nul

exit
```

**参数说明**

```bash
net [stop|start] 服务名（sql service 实例名）
```
