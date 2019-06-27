---
title: SpringBoot 自动配置原理
tags: [Java, Spring]
created: '2019-06-27T05:14:15.339Z'
modified: '2019-06-27T05:34:00.899Z'
---

# SpringBoot 自动配置原理

- `@Enable` 注解借助 `@Import` 的支持收集和注册特定场景相关 `bean` 的定义。
- `@EnableAutoConfiguration` 注解借助 `SpringFactoriesLoader` 进行自动配置。
- `SpringFactoriesLoader` 是 Spring 私有的扩展方案，类似于 `SPI`；会从 `META-INF/spring.factoties` 加载配置。
- `spring.factories` 格式为 `key=value`，`key` 和 `value` 都是 Java 的完整类名。

 `@EnableAutoConfiguration` 自动配置的魔法其实就是：从 classpath 中搜寻所有 `META-INF/spring.factories` 配置文件，并将其中 `org.springframework.boot.autoconfigure.EnableAutoConfiguration` 对应的配置项通过反射实例化为对应的标注了 `@Configuration` 的 `JavaConfig` 形式的 IoC 容器配置类，然后汇总为一个并加载到 IoC 容器。
