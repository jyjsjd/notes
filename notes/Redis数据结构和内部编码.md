---
tags: [Redis]
title: Redis数据结构和内部编码
created: '2019-05-14T02:46:30.957Z'
modified: '2019-12-03T08:13:18.223Z'
---

# Redis数据结构和内部编码

![redistype.png](../attachments/redistype.png)

![redisinternaltype.png](../attachments/redisinternaltype.png)

> Redis 3.2 为列表提供了quicklist编码，是以ziplist为节点的linkedlist，结合了两者的优点。
