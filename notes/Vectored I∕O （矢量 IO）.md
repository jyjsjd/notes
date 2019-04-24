---
title: Vectored I/O （矢量 IO）
created: '2019-04-24T11:40:20.991Z'
modified: '2019-04-24T11:45:54.463Z'
---

# Vectored I/O （矢量 IO）

- In the context of a `write` operation, the contents of several buffers are `gathered` (drained) in sequence and then sent through the channel to a `destination`. These buffers are not required to have identical capacities.
- In the context of a `read` operation, the contents of a channel are `scattered` (filled) to multiple `buffers` in sequence; each buffer is filled to its limit until the channel is empty or until the total buffer space is used.
