---
title: Java -D 参数
created: '2019-04-13T09:05:10.572Z'
modified: '2019-04-13T09:15:28.292Z'
tags: [Java]
---

# Java -D 参数

`-Dproperty=value`

Sets a system property value.

If value is a string that contains spaces, then you must enclose the string in double quotation marks:

java -Dmydir="some string" SomeClass

获取参数：
`System.getProperty("mydir")`
