---
tags: [Java]
title: JVM方法调用
created: '2019-09-10T05:50:28.540Z'
modified: '2019-09-10T05:56:40.287Z'
---

# JVM方法调用

- invokestatic：调用**静态方法**。
- invokespecial：调用**实例构造器**、**私有方法**和**父类方法**。
- invokevirtual：调用所有**虚方法**。
- invokeinterface：调用**接口方法**，会在运行时再确定实现接口的对象方法。
- invokedynamic：在运行时动态解析出调用点限定符所引用的方法，然后再去执行该方法。

虚方法：能被*invokestatic*和*invokespecial*指令调用的方法，都是可以在解析阶段中确定的，符合这个条件的有静态方法、私有方法、实例构造器和父类方法。这些方法可以成为**非虚方法**；其他方法称为**虚方法**。
