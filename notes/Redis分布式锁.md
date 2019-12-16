---
tags: [Redis]
title: Redis分布式锁
created: '2019-12-14T00:43:58.784Z'
modified: '2019-12-16T03:41:15.146Z'
---

# Redis分布式锁

## setnx

`setnx`只有在key不存在时才会设置成功：

```
SET resource_name my_random_value NX PX 30000
```

释放锁用lua脚本，只有value一样时才删除：

```lua
if redis.call("get",KEYS[1]) == ARGV[1] then
    return redis.call("del",KEYS[1])
else
    return 0
end
```

## redlock

1. 获取当前时间戳，单位是毫秒；
2. 轮流尝试在每个`master`节点上创建锁，过期时间较短，一般就几十毫秒；
3. 尝试在大多数节点上建立一个锁，比如5个节点就要求是3个节点`n/2+1`；
4. 客户端计算建立好锁的时间，如果建立锁的时间小于超时时间，就算建立成功了；
5. 要是锁建立失败了，那么就依次之前建立过的锁删除；
6. 只要别人建立了一把分布式锁，你就得不断**轮询**去尝试获取锁。
