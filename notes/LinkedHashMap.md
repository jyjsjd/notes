---
tags: [Java]
title: LinkedHashMap
created: '2019-11-02T08:00:36.364Z'
modified: '2019-11-02T08:07:29.075Z'
---

# LinkedHashMap

可以维持两种顺序：
- 插入顺序；
- 最近访问顺序，从最久未访问到最近访问。
  > A special LinkedHashMap(int,float,boolean) constructor is provided to create a linked hash map whose order of iteration is the order in which its entries were last accessed, from least-recently accessed to most-recently (access-order).

```java
    /**
     * Constructs an empty <tt>LinkedHashMap</tt> instance with the
     * specified initial capacity, load factor and ordering mode.
     *
     * @param  initialCapacity the initial capacity
     * @param  loadFactor      the load factor
     * @param  accessOrder     the ordering mode - <tt>true</tt> for
     *         access-order, <tt>false</tt> for insertion-order
     * @throws IllegalArgumentException if the initial capacity is negative
     *         or the load factor is nonpositive
     */
    public LinkedHashMap(int initialCapacity,
                         float loadFactor,
                         boolean accessOrder) {
        super(initialCapacity, loadFactor);
        this.accessOrder = accessOrder;
    }
```
---

接口和父类：
```java
public class LinkedHashMap<K,V>
    extends HashMap<K,V>
    implements Map<K,V>
```

插入删除操作都是调用`HashMap`的方法实现。

---

如何维持顺序？

HashMap在插入、删除操作之后都会调用LinkedHashMap的回调函数：
```java
    // Callbacks to allow LinkedHashMap post-actions
    void afterNodeAccess(Node<K,V> p) { }
    void afterNodeInsertion(boolean evict) { }
    void afterNodeRemoval(Node<K,V> p) { }
```
