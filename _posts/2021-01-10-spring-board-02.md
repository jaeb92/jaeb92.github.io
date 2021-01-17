---
title: "Spring MVC 게시판 구현하기 (2) - Apache Tomcat 서버 설정"
categories: Spring
---

>.
>포스트 진행 순서
>1. Eclipse 프로젝트 생성 및 기본 설정
>2. Apache Tomcat 서버 설정
>3. MySQL 설치
>4. DB 생성 및 Mybatis 연동
>5. CURD 구현
>6. 추후 예정..
>.

이전 포스트에서는 Eclipse에 Spring project를 생성하는 방법, pom.xml파일에 프로젝트 진행에 있어 필요한 dependency들 그리고 한글 인코딩 설정하는 내용을 다뤘습니다. 이번 포스트에서는 Apache Tomcat 서버를 설정하는 방법을 다뤄보도록 하겠습니다.

# 2. Apache Tomcat 서버 설정

- [Apache Tomcat 9.0](https://tomcat.apache.org/download-90.cgi "apache tomcat 9.0 download") 

---
위 링크로 이동한 뒤 원하는 형태로 다운로드를 진행하시면 됩니다.

저는 **zip파일**을 다운 받아 진행하였습니다. 

![spring-6](https://user-images.githubusercontent.com/42923027/104121713-c2dcbf00-5383-11eb-8fec-ecb9c81e0a40.png)

---

zip파일을 원하는 경로에 다운로드 받으신 뒤 압축을 해제하면 다음과 같은 파일들이 생성됩니다. 

![spring-7](https://user-images.githubusercontent.com/42923027/104121759-0fc09580-5384-11eb-85b2-e448dd25a3cb.png)


---

다시 eclipse로 돌아와 Server 창에서 "No Servers are available ... "를 클릭해주세요

![spring-8](https://user-images.githubusercontent.com/42923027/104121773-3a125300-5384-11eb-9282-2d97344f6674.png)


---
Tomcat v9.0 Server를 선택하시고 다운 받은 Apache Tomcat의 경로로 지정해준 뒤 Finish를 해주세요

![spring-9](https://user-images.githubusercontent.com/42923027/104121810-8cec0a80-5384-11eb-8788-130ab7a45b5c.png)

---

해당 서버가 사용할 포트를 설정해주시면 되는데 보통 8080이 기본 포트로 설정되어있습니다.
저는 8080 포트 그대로 진행하였습니다.

![spring-10](https://user-images.githubusercontent.com/42923027/104121843-c6247a80-5384-11eb-82be-d6336de5097a.png)


---

포트까지 설정을 마친 뒤 Modules탭 >> Add Web Modules... >> 프로젝트 선택 >> ok<br/>

![spring-12](https://user-images.githubusercontent.com/42923027/104122041-046e6980-5386-11eb-9bfa-67c6021546e0.png)


---

위 단계까지 진행한 뒤 브라우저를 열고 localhost:8080에 접속하면 다음과 같은 화면을 볼 수 있습니다.<br/>
(페이지의 내용은 제가 수정했습니다.)

![spring-11](https://user-images.githubusercontent.com/42923027/104121969-8f029900-5385-11eb-95dd-ac3796af1091.png)


---


이상 Apache Tomcat 서버를 적용해봤습니다. 아직까지는 크게 어려운 부분이 없다고 생각해서 따라오는 데 무리가 없을 거라고 생각합니다.  다음 포스트에서는 MySQL을 설치하는 과정을 다뤄보고 그 이후부터 데이터베이스 및 필요한 테이블들을 생성해주고 프로젝트에 연동이 되는지 간단한 테스트까지 진행해보도록 하겠습니다.

