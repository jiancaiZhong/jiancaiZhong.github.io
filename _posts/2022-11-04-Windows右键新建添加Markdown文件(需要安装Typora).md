---
layout: mypost
title: Windows右键新建添加Markdown文件(需要安装Typora)
categories: [Windows]
---

新建文件，后缀名为`reg`，文件内容如下。

```bash
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\.md]
@="Typora.md"
"Content Type"="text/markdown"
"PerceivedType"="text"

[HKEY_CLASSES_ROOT\.md\ShellNew]
"NullFile"=""
```

双击运行，添加到注册表即可。
