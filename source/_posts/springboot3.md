---
title: Spring Boot Tutorial 3 (使用@Async实现异步调用)
date: 2016-05-17 09:45:40
tags: spring boot
---

* 必须在SpringBootApplication类中注解声明,启用异步调用

```java
@SpringBootApplication
@EnableAsync
public class Application {

}
```

* 使用@Async注解就能简单的将原来的同步函数变为异步函数

```java
@Component
public class Task {
    @Async
    public void doTaskOne() throws Exception {

    }

    @Async
    public void doTaskTwo() throws Exception {

    }

}
```
