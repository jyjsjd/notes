---
title: Reflection 和 MethodHandle 机制
tags: [Java]
created: '2019-06-25T08:16:16.303Z'
modified: '2019-06-25T08:19:53.892Z'
---

# Reflection 和 MethodHandle 机制

- Reflection 是在模仿 Java 代码层次的方法调用，MethodHandle 是在模拟字节码层次的方法调用。
- Reflection 中包含的信息远比 MethodHandle 多。

MethodHandles.lookup 的三个方法：

- findStatic(): invokestatic
- findVirtual(): invokevirtual&invokeinterface
- findSpecial(): invokespecial
