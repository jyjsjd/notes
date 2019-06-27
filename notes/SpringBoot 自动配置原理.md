---
title: SpringBoot 自动配置原理
tags: [Java, Spring]
created: '2019-06-27T05:14:15.339Z'
modified: '2019-06-27T05:29:55.686Z'
---

# SpringBoot 自动配置原理

- `@Enable` 注解借助 `@Import` 的支持收集和注册特定场景相关 `bean` 的定义。
- `@EnableAutoConfiguration` 注解借助 `SpringFactoriesLoader` 进行自动配置。
- `SpringFactoriesLoader` 是 Spring 私有的扩展方案，类似于 `SPI`；会从 `META-INF/spring.factoties` 加载配置。
- `spring.factories` 格式为 `key=value`，`key` 和 `value` 都是 Java 的完整类名。
