---
title: proto
tags: [JavaScript]
created: '2019-01-23T09:08:16.882Z'
modified: '2019-03-15T03:44:55.016Z'
---

# `__proto__`

`__proto__` 是**实例对象**的属性。

prototype 是**函数**（或者类）的属性。

```javascript
Object.getPrototypeOf( a ) === Foo.prototype; // true

a.__proto__ === Foo.prototype; // true
```

---

实例对象的 `.constructor` 引用同样被委托给了 `Foo.prototype` ， 而 `Foo.prototype.constructor` 默认指向 Foo 。
