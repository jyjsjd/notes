---
tags: [Java, JVM]
title: volatile 内存屏障
created: '2019-02-28T02:40:00.195Z'
modified: '2019-12-14T01:34:49.654Z'
---

# volatile 内存屏障
`volatile` 关键字：
* 保证可见性、不保证原子性；
* 禁止指令重排序。

`volatile` 关键字修饰的变量，赋值后会多执行一次 `lock addl $0x0, (%esp)` 指令。这称为**内存屏障**。它使得本CPU的cache写入了内存并且使别的CPU的内存失效，可以让前面的修改对其他CPU立即可见。
内存屏障是一组处理指令，用来实现对内存操作的顺序限制。`volatile` 的底层就是通过内存屏障来实现的。`volatile` 变量在写操作之后会插入一个 `store 屏障`，在读操作之前会插入一个 `load 屏障`。
