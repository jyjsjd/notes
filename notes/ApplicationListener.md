---
tags: [Java, Spring]
title: ApplicationListener
created: '2019-11-22T09:37:47.845Z'
modified: '2019-11-25T02:49:06.483Z'
---

# ApplicationListener

|  事件   | 解释  |
|  ----  | ----  |
| ContextRefreshedEvent  | 容器调用refresh方法之后：所有的Bean都已准备就绪、实现BeanPostProcesser的Bean都已经触发、单例都已经实例化、容器已经准备好之后被调用。 |
| ContextStartedEvent    | 容器调用start方法之后：实现LifeCycle接口的Bean明确收到了start的信号之后。 |
| ContextStoppedEvent    | 容器调用stop方法之后：实现LifeCycle接口的Bean明确收到stop信号之后。调用了stop方法的容器可以再次调用start方法。 |
| ContextClosedEvent     | 容器调用close方法之后：所有单例的Bean都被销毁；调用了close方法的容器不能再次refresh或restart。 |
| RequestHandledEvent    | web专用的事件。在HTTP请求完成之后调用。只适用于使用DispatchServlet的请求。 |
