---
title: "Spring MVC 게시판 구현하기 (1) - 프로젝트 생성 및 환경설정"
layout: categories
permalink: /categories/Spring/
categories: Spring
---


오래전에 스프링으로 게시판을 만들어 본 경험이 있지만 현재는 다른 프로젝트를 진행하다 보니 자바, 스프링을 소홀히 한 감이 있습니다. 그래서 다시 공부도 할 겸 Spring + Mysql + Mybatis + Apache Tomcat 정도로 간단한 게시판을 구현해보려 합니다. 


순서는 다음과 같습니다.

1. Eclipse 프로젝트 생성 및 기본 설정
2. Apache Tomcat 서버 설정
3. DB 생성 및 연동
4. CURD 구현
5. 추후 예정..

일단 가볍게 진행을 해보고 가능하면 다양한 기능을 추가하고 외부 API까지 활용하는 방향으로 진행해보도록 하겠습니다. 



# 1. Eclipse 프로젝트 생성 및 기본설정

- 프로젝트 생성과정
- pom.xml dependency 추가 및 버전 설정



우선 new --> Spring Legacy Project 선택해주세요


![spring-1](https://user-images.githubusercontent.com/42923027/104120867-77271700-537d-11eb-8edc-701c92e8742f.png)


---

Spring MVC Project, project name 설정한 뒤 'next' 진행해주세요

![spring-2](https://user-images.githubusercontent.com/42923027/104120878-945be580-537d-11eb-9fcc-f80ebb1e097d.png)


---

프로젝트 패키지명을 설정한 뒤 "FINISH" 해주세요

![spring-3](https://user-images.githubusercontent.com/42923027/104120914-d2590980-537d-11eb-9f30-b45b4a5d76ce.png)


---

프로젝트가 정상적으로 생성되었다면 pom.xml파일을 열어 각종 dependency들을 설정해줍니다.


추가해준 dependency 

- MySQL Connector/J » 8.0.22
- MyBatis » 3.5.6
- MyBatis Spring » 2.0.6
- Spring JDBC » 5.2.12.RELEASE
- Spring TestContext Framework » 5.2.12.RELEASE



```
<properties>
    <java-version>1.8</java-version>
    <org.springframework-version>5.2.12.RELEASE</org.springframework-version>
    <org.aspectj-version>1.9.6</org.aspectj-version>
    <org.slf4j-version>1.7.25</org.slf4j-version>
</properties>

...
...
...

<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-test</artifactId>
    <version>${org.springframework-version}</version>
    <scope>test</scope>
</dependency>

<!-- https://mvnrepository.com/artifact/org.springframework/spring-jdbc -->
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-jdbc</artifactId>
    <version>${org.springframework-version}</version>
</dependency>

<!-- https://mvnrepository.com/artifact/org.mybatis/mybatis-spring -->
<dependency>
    <groupId>org.mybatis</groupId>
    <artifactId>mybatis-spring</artifactId>
    <version>2.0.6</version>
</dependency>

<!-- https://mvnrepository.com/artifact/org.mybatis/mybatis -->
<dependency>
    <groupId>org.mybatis</groupId>
    <artifactId>mybatis</artifactId>
    <version>3.5.6</version>
</dependency>

<!-- https://mvnrepository.com/artifact/mysql/mysql-connector-java -->
<dependency>
    <groupId>mysql</groupId>
    <artifactId>mysql-connector-java</artifactId>
    <version>8.0.22</version>
</dependency>
```

![spring-4](https://user-images.githubusercontent.com/42923027/104120925-fa486d00-537d-11eb-8ce4-cf4ec92c3f8c.png)


---


web.xml에 한글 필터 추가하기

- src > main > webapp > WEB-INF > web.xml 파일에 다음을 입력해주세요
  
```
<!-- 한글설정 -->
<filter>
    <filter-name>encodingFilter</filter-name>
    <filter-class>
        org.springframework.web.filter.CharacterEncodingFilter
    </filter-class>
    <init-param>
        <param-name>encoding</param-name>
        <param-value>UTF-8</param-value>
    </init-param>
    <init-param>
        <param-name>forceEncoding</param-name>
        <param-value>true</param-value>
    </init-param>
</filter>
<filter-mapping>
    <filter-name>encodingFilter</filter-name>
    <url-pattern>/*</url-pattern>
</filter-mapping>
<!-- 한글설정 END -->
```


이상 프로젝트 생성 및 기본 설정들을 마쳤고 다음은 Apache Tomcat을 설정해보도록 하겠습니다.
