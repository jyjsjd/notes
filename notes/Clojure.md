---
title: Clojure
created: '2019-06-29T08:37:39.527Z'
modified: '2019-07-08T06:55:13.318Z'
tags: [Clojure]
---

# Clojure

## Clojure 语法

![clojure_call.png](../attachments/clojure_call.png)

--- 

## Clojure 集合

![clojure_collection.png](../attachments/clojure_collection.png)

---

## 集合操作

![clojure_collection1.png](../attachments/clojure_collection1.png)

---

## 并发操作

- Coordination. A coordinated operation is one where multiple actors must cooperate (or, at a minimum, be properly sequestered so as to not interfere with each other) in order to yield correct results.

- Synchronization. Synchronous operations are those where the caller’s thread of execution waits or blocks or sleeps until it may have exclusive access to a given context, whereas asynchronous operations are those that can be started or scheduled without blocking the initiating thread of execution.

![clojure_ref.png](../attachments/clojure_ref.png)

---

`#` 匿名函数；set 以 `#` 开头
`%` 代表参数
`&` 定参和变参的分界符
`!` 突变函数以感叹号结尾
`:` map 的 key 以冒号开头；关键字以冒号开头
`'` list 以单引号开头

