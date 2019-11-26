---
tags: [Spring]
title: Spring方法替换
created: '2019-11-26T07:37:46.111Z'
modified: '2019-11-26T08:39:28.363Z'
---

# Spring方法替换

注入时几种替换的方法：

| 类别 | XML属性 | 注解 | 
| ---- | ---- | ---- | 
| 静态工厂 | factory-method |  |
| 非静态工厂 | factory-bean factory-method |  |
| FactoryBean |  |  |
|  |  | lookup-method |
| ObjectFactoryCreatingFactoryBean |  |  |
| MethodReplacer | replaced-method |  |


## 静态工厂方法

```java
public class StaticFactory {
  public static Bar getInstance(Foo foo) {
    return new Bar();
  }
}
```

## 非静态工厂方法

```java
public class NonStaticFactory {
  public Bar getInstance() {
    return new Bar();
  }
}
```

## FactoryBean

如果对象的初始化过程复杂，可以将其放在FactoryBean中，引用时直接ref FactoryBean的实现类。

```java
public interface FactoryBean<T> {
  /**
   * 返回一个实例。 
   */
	T getObject() throws Exception;
	/**
   * 返回FactoryBean创建的实例类型。 
   */
	Class<?> getObjectType();
  /**
   * 是否单例。 
   */ 
	boolean isSingleton();
}
```

## lookup-method

通常用在singleton的Bean引用prototype的Bean时，被引用的Bean每次返回的的对象都是一样的。
在设置对象时可以试用lookup-method：
```xml
<lookup-method name="xxx" method="getXxx" />
```

## ObjectFactoryCreatingFactoryBean

## MethodReplacer
