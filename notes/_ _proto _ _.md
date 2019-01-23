---
title: \_\_proto\_\_
tags: [JavaScript]
---

# \_\_proto\_\_

\_\_proto\_\_ 是**实例对象**的属性。

prototype 是**函数**（或者类）的属性。

```javascript
Object.getPrototypeOf( a ) === Foo.prototype; // true

a.__proto__ === Foo.prototype; // true
```

---

实例对象的 `.constructor` 引用同样被委托给了 `Foo.prototype` ， 而 `Foo.prototype.constructor` 默认指向 Foo 。
