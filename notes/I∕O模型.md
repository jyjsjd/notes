---
tags: [Java, NIO]
title: I/O模型
created: '2019-09-11T08:27:28.347Z'
modified: '2019-12-15T12:19:30.338Z'
---

# I/O模型

- 阻塞I/O
- 非阻塞I/O
- I/O复用（select、poll、linux 2.6种改进的epoll）
- 信号驱动IO（SIGIO）
- 异步I/O（POSIX的aio_系列函数）

![unix_io_model.jpg](../attachments/unix_io_model.jpg)

- 传统的Java BIO (blocking I/O)是 Unix I/O 模型中的第一种。
- Java NIO 中如果不使用 select 模式，而只把 channel 配置成 nonblocking 则是第二种模型。
- Java NIO select 实现的是一种多路复用I/O，底层使用 epoll 或者相应的 poll 系统调用。
- 第四种模型 JDK 没有实现。
- Java NIO2 增加了对第五种模型的支持，也就是 AIO。
