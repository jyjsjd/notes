---
title: Object.create()
tags: [JavaScript]
---

# Object.create()

`Object.create()` 方法创建一个新对象，使用现有的对象来提供新创建的对象的 `__proto__`。

```javascript
var foo = { 
  something: function () { 
    console.log( "Tell me something good..." ); 
  } 
};

var bar = Object.create( foo );

bar.something(); // Tell me something good...
```

---

`Object.create()` 会创建一个新对象（bar）并把它关联到我们指定的对象（foo）， 这样 我们就可以充分发挥 [[Prototype]] 机制的威力（委托）并且避免不必要的麻烦（比如使用 `new` 的构造函数调用会生成 `.prototype` 和 `.constructor` 引用）。

---

`Object.create(null)` 会创建一个拥有空（或者说null）[[Prototype]] 链接的对象， 这个对象无法进行委托。由于这个对象**没有原型链**，所以 `instanceof` 操作符无法进行判断， 因此总是会返回 false 。
