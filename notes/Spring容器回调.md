---
tags: [Spring]
title: Spring容器回调
created: '2019-11-26T06:36:10.922Z'
modified: '2019-11-26T07:35:03.421Z'
---

# Spring容器回调

|  接口   | 方法  | 注解 | XML属性 | 解释 |
|  ----  | ----  | ---- | ---- | ---- |
| BeanFactoryPostProcessor | postProcessBeanFactory ||| 在容器实例化对象之**前**对注册到容器的`BeanDefinition`的信息做相应修改 |
| BeanPostProcessor | postProcessBeforeInitialization ||| 在对象实例化之**前**执行 |
| BeanPostProcessor | postProcessAfterInitialization ||| 在对象实例化之**后**执行 |
| InitializingBean | afterPropertiesSet | @PostConstruct |init-method | 在调用完`BeanFactoryPostProcessor#postProcessBeanFactory`之**后**执行 |
| DisposableBean | destroy | @PreDestory | destroy-method |单例对象销毁之前执行|


- `PropertyPlaceholderConfigurer`，`PropertyOverrideConfigurer`，`CustomEditorConfigurer`等是通过`BeanFactoryPostProcessor`实现的
- `BeanNameAware`，`BeanFactoryAware`，`ApplicationContextAware`等接口就是通过`BeanPostProcessor`实现的。
