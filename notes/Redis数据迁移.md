---
tags: [Redis]
title: Redis数据迁移
created: '2019-11-12T11:12:04.808Z'
modified: '2019-12-16T03:41:06.185Z'
---

# Redis数据迁移

## Move 

```
move key db
```

move用于在Redis内部进行数据迁移，从一个db迁移到另一个db。

## dump + restore

```
dump key
restore key ttl value
```

dump + restore实现的是不同Redis实例间的数据迁移：
1. 在源Redis上dump将键值序列化，采用**RDB**格式。
2. 在目标Redis上，restore将序列化的值进行复原，ttl代表过期时间。

## migrate

```
migrate host port key destination-db timeout [copy] [replace]
```

- copy：不移除源Redis上的key。
- replace：替换目标Redis上已存在的key。

migrate用于Redis实例间的数据迁移，实际上就是将dump、restore、del命令组合。

1. 整个过程是**原子**执行的，只需在源Redis上执行migrate。
2. migrate的数据传输直接在源Redis和目标Redis上完成。
3. 目标Redis完成restore会发送OK给源Redis，源Redis会根据migrate对应的选项决定是否删除对应的键。
