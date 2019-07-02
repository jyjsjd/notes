---
title: AWK 简单使用
created: '2019-05-21T05:52:09.452Z'
modified: '2019-07-02T08:04:19.225Z'
tags: [Shell]
---

# AWK 简单使用

```shell
awk 'program' input files
```

其中，`program` 是一个 `pattern { action }` 的*序列*。

如：

```shell
awk '$3 > 0 { print $1, $2 * $3 }' emp.data
```
