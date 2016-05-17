---
title: Spring Boot Tutorial 2 (使用@Scheduled创建定时任务)
date: 2016-05-17 09:32:31
tags: spring boot
---

使用spring boot 做一些定时任务，例如定时给平台注册会员发送推荐邮件。

## 创建定时任务

* 首先，必须在SpringBootApplication类中注解声明启用定时任务

``` java
@SpringBootApplication
@EnableScheduling
public class Application {

}
```

* 然后，具体实现类

``` java
@Component
public class ScheduledTasks {

    private static final SimpleDateFormat dateFormat = new SimpleDateFormat("HH:mm:ss");

    @Scheduled(fixedRate = 6000)
    public void reportCurrentTime() {
        System.out.println("当前时间：" + dateFormat.format(new Date()));
    }

}
```

## 说明

* @Scheduled(fixedRate = 5000) ：上一次开始执行时间点之后5秒再执行

* @Scheduled(fixedDelay = 5000) ：上一次执行完毕时间点之后5秒再执行

* @Scheduled(initialDelay=1000, fixedRate=5000) ：第一次延迟1秒后执行，之后按fixedRate的规则每5秒执行一次

* @Scheduled(cron="*/5 * * * * *") ：通过cron表达式定义规则




