---
tags: [Redis]
title: Redis常用命令
created: '2019-12-03T07:46:07.100Z'
modified: '2019-12-16T03:41:24.925Z'
---

# Redis常用命令

`--` 开头的命令和`redis-cli -h {host} -p {port}`一起使用。

- `setnx`：key 必须不存在才能设置成功，用于新增；
- `setxx`：key 必须存在才能设置成功，用于修改；
- `slowlog`：慢查询列表；
- `object refcount {key}`：key的引用计数；
- `object encoding {key}`：key的内部类型；
- `--bigkeys`：统计大对象；
- `--stat`：获取当前Redis使用情况；
