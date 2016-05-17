---
title: Spring Boot Tutorial 1 (@SpringBootApplication)
date: 2016-05-14 22:40:50
tags: spring boot
---

## @SpringBootApplication

``` java
@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Inherited
@Configuration
@EnableAutoConfiguration
@ComponentScan
public @interface SpringBootApplication {

    /**
     * Exclude specific auto-configuration classes such that they will never be applied.
     * @return the classes to exclude
     */
    Class<?>[] exclude() default {};

}
```

@Configuration : 表示Application作为sprig配置文件存在
@EnableAutoConfiguration: 启动spring boot内置的自动配置
@ComponentScan : 扫描bean，路径为Application类所在package以及package下的子路径
