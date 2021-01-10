---
title: "Spring MVC 게시판 구현하기 (1) - 프로젝트 생성 및 환경설정"
layout: categories
permalink: /categories/Spring/
categories: Spring
---


오래전에 스프링으로 게시판을 만들어 본 경험이 있지만 현재는 다른 프로젝트를 진행하다 보니 <br/>자바(스프링)를 조금 소홀히 한 감이 있습니다. 그래서 다시 공부도 할 겸 spring + mysql + mybatis 정도로<br/>간단한 게시판을 구현해보려 합니다. 


순서는 다음과 같습니다.

1. eclipse 프로젝트 생성 및 기본 설정
2. DB 생성 및 연동
3. CURD 구현
4. 추후 예정..

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

![spring-4](https://user-images.githubusercontent.com/42923027/104120925-fa486d00-537d-11eb-8ce4-cf4ec92c3f8c.png)

