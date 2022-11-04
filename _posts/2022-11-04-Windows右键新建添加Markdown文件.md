---
layout: mypost
title: Windows右键新建添加md文件
categories: [Windows]
---

> Windows右键-新建 添加新建Markdown文件的快捷键

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