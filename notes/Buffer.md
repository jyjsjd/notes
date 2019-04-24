---
title: Buffer
created: '2019-04-24T06:22:08.051Z'
modified: '2019-04-24T06:29:17.252Z'
tags: [Java]
---

# Buffer

- **Capacity**: The `total number` of data items that can be stored in the buffer. The capacity is specified when the buffer is created and cannot be changed later.
- **Limit**: The zero-based `index` of the first element that should `not` be read or written. In other words, it identifies the number of “live” data items in the buffer.
- **Position**: The zero-based index of the next data item that `can` be read or the location where the data item can be written.
- **Mark**: A zero-based index to which the buffer’s position will be `reset` when the buffer’s reset() method (presented shortly) is called. The mark is initially undefined.

These four properties are related as follows: 0 <= mark <= position <= limit <= capacity
