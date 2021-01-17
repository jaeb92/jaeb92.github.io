---
title: "Spring MVC 게시판 구현하기 (2) - Apache Tomcat 서버 설정"
layout: categories
permalink: /categories/Spring/
categories: Spring
---
>.
>포스트 진행 순서
>1. Eclipse 프로젝트 생성 및 기본 설정
>2. Apache Tomcat 서버 설정
>3. DB 생성 및 Mybatis 연동
>4. CURD 구현
>5. 추후 예정..
>.


이전 포스트에서는 Apache Tomcat 서버를 설정하는 방법을 다뤄보았습니다. 이번 포스트에서는 Database 생성, 테이블 생성 그리고 mybatis 연동까지 다뤄보도록 하겠습니다.

# 3. DB 생성 및 연동

우선 MySQL과 MySQL Workbench 설치를 진행하겠습니다. 아래의 링크로 이동한 뒤에 "MySQL Community Sever"를 클릭해주세요

- [MySQL download](https://dev.mysql.com/downloads/ "mysql download")


![spring-13](https://user-images.githubusercontent.com/42923027/104190592-a746e680-545f-11eb-82a2-3ca4c13bd5da.png)

---

자신의 운영체제에 맞게 다운로드를 해주시면 됩니다. 저는 Windows 64bit로 진행하였습니다.<br/>
``` 
msi로 설치하면 32bit, 64bit 다 설치가 가능하다고 안내가 되어있지만 Archive로 설치해보도록 하겠습니다
```

![spring-14](https://user-images.githubusercontent.com/42923027/104194559-d2800480-5464-11eb-8d75-9d99eeadad1f.png)


---

로그인을 하기는 번거로우니 바로 "No thanks, just start my download"를 클릭해서 바로 다운로드를 진행해줍니다.

![spring-15](https://user-images.githubusercontent.com/42923027/104191046-54216380-5460-11eb-88cc-8fa35dcaec96.png)


---

다운로드를 완료하였으면 압축을 해제한 뒤에 C드라이브 아래에 MySQL 경로를 생성해주고 압축해제한 파일을 모두 Ctrl + C ,  Ctrl + V 해주세요 

![spring-16](https://user-images.githubusercontent.com/42923027/104830256-7253ed00-58c0-11eb-849e-9437ea057796.png)
