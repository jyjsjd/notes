---
tags: [Redis]
title: Redis内存回收策略
created: '2019-12-16T03:41:27.282Z'
modified: '2019-12-16T03:45:31.972Z'
---

# Redis内存回收策略

- noeviction: 默认策略，当内存不足以容纳新写入数据时，新写入操作会报错。
- volatile-lru：在设置了过期时间的键中移除最近最少使用的key。
- allkeys-lru：移除最近最少使用的key。
- allkeys-random：随机移除某个key。
- volatile-random：在设置了过期时间的键空间中，随机移除过期的key。
- volatile-ttl：在设置了过期时间的键空间中，优先移除过期时间更早的key。
