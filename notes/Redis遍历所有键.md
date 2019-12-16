---
tags: [Redis]
title: Redis遍历所有键
created: '2019-11-12T11:28:34.440Z'
modified: '2019-12-16T03:40:58.542Z'
---

# Redis遍历所有键

## 全量遍历

```
key pattern
```

pattern是通配符。

key命令会造成阻塞。

## 渐进式遍历

```
scan cursor [match pattern] [count number]
```

- cursor是游标，从0开始，每次scan完成都会返回当前游标，供下次使用，0表示遍历结束。
- match patter是模式匹配。
- count number表明每次要遍历的键的个数，默认10。

还有专用于一种类型的scan命令：
- sscan
- hscan
- zscan

> scan 不能保证完整地遍历出所有键。
