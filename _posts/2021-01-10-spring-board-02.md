---
title: "Spring MVC 게시판 구현하기 (2) - Apache Tomcat 서버 설정"
layout: categories
permalink: /categories/Spring/
categories: Spring
---

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
