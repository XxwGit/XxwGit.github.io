---
layout: post
title: "Spring Boot环境搭建"
subtitle: "SpringBoot到底应该怎样学？"
author: "XXW"
header-img: "img/post-bg-2015.jpg"
header-img-credit: "@WebdesignerDepot"
header-img-credit-href: "medium.com/@WebdesignerDepot/poll-should-css-become-more-like-a-programming-language-c74eb26a4270"
header-mask: 0.4
catalog:true
tags:
  - Spring
  - SpringBoot
  - 微服务框架
  - SpringCloud
---

> 刚刚接触SpringBoot，对于SpringBoot知之甚少，特此开此博客记录SpringBoot学习路。

### Spring Boot开发环境：
1. jdk配置
2. eclipse安装
3. Gradle的安装配置
4. STS安装

### 创建Spring Boot简单实例:
1. 首先创建一个Gradel的项目；
2. 随后针对项目的build.gradel文件进行配置；
3. 最后在xxxApplication.java所在目录下进行创建包进行项目的编写即可

### Gradle配置详解：
```
plugins {
	id 'org.springframework.boot' version '2.1.5.RELEASE'
	id 'java'
}

apply plugin: 'io.spring.dependency-management'

group = 'com.example'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '1.8'

repositories {
	mavenCentral()
}

dependencies {
	compile 'org.springframework.boot:spring-boot-starter-web'
	testImplementation 'org.springframework.boot:spring-boot-starter-test'
}

```

### 启动类代码展示:
```
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class SpringBootDemoApplication {

	public static void main(String[] args) {
		SpringApplication.run(SpringBootDemoApplication.class, args);
	}

}

```

### 测试小例子:
```
@RestController
public class Example {
    @RequestMapping("/")
    String home() {
        return "Hello World!";
    }
}
```
> 其中注意RestController和Controller的区别，如果使用Controller还需要配合ResponseBody一起使用.

### 浏览器测试:
1. 在浏览器中输入http://localhost:8080即可看到运行结果
2.  如果在application.properties中设置了server.context-path=/spring-boot/，那么需要在浏览器中输入http://localhost:8080/spring-boot/