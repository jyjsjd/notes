---
title: JavaScript 属性屏蔽
tags: [JavaScript]
---

# JavaScript 属性屏蔽


1. 如果在 [[Prototype]] 链上层**存在**名为 foo 的普通数据访问属性并且**没有被标记为只读**（ writable:false ）， 那就会直接在 myObject 中添加一个名为 foo 的新 属性，它是**屏蔽属性**。

2. 如果在 [[Prototype]] 链上层**存在** foo ， 但是它被标记为**只读**， 那么无法修改已有属性或者在 myObject 上创建屏蔽属性。如果运行在严格模式下，代码会抛出一个错误。否则，这条赋值语句会被忽略。总之，不会发生屏蔽。

3. 如果在 [[Prototype]] 链上层**存在** foo 并且它是一个 **setter**，那就一定会 调用这个 setter。 foo 不会被添加到（或者说屏蔽于） myObject ，也不会重新定义 foo 这 个 setter。

如果你希望在第二种和第三种情况下也屏蔽 foo ，那就不能使用 = 操作符来赋值，而是使用 `Object.defineProperty()` 来向 myObject 添加 foo 。
