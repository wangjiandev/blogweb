---
title: Spring Boot Tutorial 3 (多环境配置)
date: 2016-05-17 10:01:40
tags:
---

## 多环境配置

我们在开发Spring Boot应用时，通常同一套程序会被应用和安装到几个不同的环境，比如：开发、测试、生产等。其中每个环境的数据库地址、服务器端口等等配置都会不同，如果在为不同环境打包时都要频繁修改配置文件的话，那必将是个非常繁琐且容易发生错误的事。

对于多环境的配置，各种项目构建工具或是框架的基本思路是一致的，通过配置多份不同环境的配置文件，再通过打包命令指定需要打包的内容之后进行区分打包，Spring Boot也不例外，或者说更加简单。

> 在Spring Boot中多环境配置文件名需要满足[application-{profile}.properties]()的格式，其中[{profile}]() 对应你的环境标识，比如：
* application-dev.properties：开发环境
* application-test.properties：测试环境
* application-prod.properties：生产环境


至于哪个具体的配置文件会被加载，需要在application.properties文件中通过spring.profiles.active属性来设置，其值对应{profile}值。

> 如：[spring.profiles.active=test]()就会加载[application-test.properties]()配置文件内容

application.properties设置
> spring.profiles.active=dev 默认以dev环境设置
- java -jar xxx.jar 默认的开发环境（dev）
- java -jar xxx.jar --spring.profiles.active=test 测试环境的配置（test）
- java -jar xxx.jar --spring.profiles.active=prod 生产环境的配置（prod）

