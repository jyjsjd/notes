---
title: CAS
created: '2019-03-08T09:00:26.133Z'
modified: '2019-03-08T09:05:31.801Z'
tags: [Java]
---

# CAS

CAS操作包含三个操作数 —— `内存位置`、`预期原值`及`新值`。执行CAS操作的时候，将内存位置的值与预期原值比较，如果相匹配，那么处理器会自动将该位置值更新为新值，否则，处理器不做任何操作。CAS是一条CPU的`原子指令`（cmpxchg指令），不会造成所谓的数据不一致问题，Unsafe提供的CAS方法（如compareAndSwapXXX）底层实现即为CPU指令cmpxchg。
