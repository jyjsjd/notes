---
tags: [Redis]
title: Redis持久化
created: '2019-11-13T08:59:05.190Z'
modified: '2019-12-16T03:41:21.375Z'
---

# Redis持久化

## RDB

RDB是把当前进程数据生成**快照**保存到硬盘的过程。

### 手动触发

```
save
```
阻塞当前Redis服务器，知道RDB过程完成为止。

```
bgsave
```
Redis进程执行fork创建子进程，RDB过程由子进程完成。阻塞只发生在fork阶段。

### 自动触发

发生在以下场景：
- 使用save相关配置，自动触发bgsave；
- 从节点执行全量复制操作；
- 执行debug reload重新加载Redis
- 执行shutdown时，如果没有开启AOF操作则执行bgsave。

### 优点

- RDB是一个紧凑压缩的二进制文件，适合备份、全量复制等场景；
- RDB恢复数据远快于AOF。

### 缺点

- RDB不能做到实时持久化；
- RDB格式在不同版本的Redis中不兼容。

## AOF

AOF（append only file）：以独立日志的方式记录每次写命令，重启时重新执行AOF中的命令。

### 步骤

#### 命令写入

写入命令追加到aof_buf（缓冲区），写入内容直接采用**文本协议格式**。

#### 文件同步

缓冲区根据对应策略向硬盘做同步操作，策略有：
- always：写入缓冲区后调用fsync同步到AOF文件；
- everysec：写入缓冲区后调用write操作。fsync由专门线程每秒调用一次；
- no：写入缓冲区后调用write操作。fsync由操作系统调用。

#### 文件重写：AOF文件越来越大需要对文件重写，达到压缩的目的；

- 手动触发：直接调用bgrewrite；
- 自动触发：根据auto-aof-rewrite-min-size和auto-aof-rewrite-percentage参数确定自动触发时机。

#### 重启加载：Redis服务重启时，加载AOF恢复数据。

优先加载AOF文件。
