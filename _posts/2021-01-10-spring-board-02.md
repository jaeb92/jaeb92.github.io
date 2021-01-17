---
title: "Spring MVC 게시판 구현하기 (3) - MySQL 설치"
layout: categories
permalink: /categories/Spring/
categories: Spring
---
>.
>포스트 진행 순서
>1. Eclipse 프로젝트 생성 및 기본 설정
>2. Apache Tomcat 서버 설정
>3. MySQL 설치
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

자신의 운영체제에 맞게 다운로드를 해주시면 됩니다. 저는 편리하게 MSI로 설치하였습니다.

![spring-19](https://user-images.githubusercontent.com/42923027/104831138-63be0380-58c9-11eb-92f8-b5f273ae38a6.png)


---


![spring-20](https://user-images.githubusercontent.com/42923027/104831150-8223ff00-58c9-11eb-9315-06824be9b89e.png)

---

로그인을 하기는 번거로우니 바로 "No thanks, just start my download"를 클릭해서 바로 다운로드를 진행해줍니다.

![spring-15](https://user-images.githubusercontent.com/42923027/104191046-54216380-5460-11eb-88cc-8fa35dcaec96.png)


---


msi파일이 다운로드되면 실행시켜서 설치를 진행합니다.
<br/>Developer Default 선택 >> Next
 
![spring-21](https://user-images.githubusercontent.com/42923027/104831757-117fe100-58cf-11eb-83a7-cf05d6dd9abb.png)


---

한 번 더 Next!

![spring-22](https://user-images.githubusercontent.com/42923027/104831776-31afa000-58cf-11eb-90d9-ef3962fdaa31.png)


---

MySQL을 설치하기 위해서는 Python 64 bit 버전이 설치돼있어야 되네요. 
[Python 공식홈페이지](https://www.python.org/downloads/ "Python Download")로 이동해서 3.8버전의 Python을 설치해주세요

(Python 자세한 설치 과정은 다음에 다루도록 하겠습니다.)
![spring-23](https://user-images.githubusercontent.com/42923027/104831791-4db34180-58cf-11eb-9421-7f0880815f25.png)



---

"Execute" 클릭해주세요.

![spring-24](https://user-images.githubusercontent.com/42923027/104831844-b0a4d880-58cf-11eb-851c-706c57b1ac8a.png)

---

MySQL연결 포트를 설정해줘야 합니다. 보통 3306번 포트가 MySQL Default 포트로 설정되기 때문에 저는 Default값으로 설정하여 진행하겠습니다.

![spring-25](https://user-images.githubusercontent.com/42923027/104831855-c7e3c600-58cf-11eb-9b1e-6f186864b50e.png)

---

Next!

![spring-26](https://user-images.githubusercontent.com/42923027/104831870-e944b200-58cf-11eb-806a-0900e73a58ef.png)

---

이제 root계정의 비밀번호를 설정해줘야 합니다. 이 비밀번호는 분실하지 않도록 유의해주세요. 그렇지 않으면 번거로운 작업들을 거쳐야 한답니다... 네...

![spring-27](https://user-images.githubusercontent.com/42923027/104831882-fb265500-58cf-11eb-8e72-4e9fcd640034.png)


이 이후의 작업들은 따로 설정해줄 필요가 없습니다. 그렇기 때문에 계속 Next, 해서 진행해주시고 

---

마지막에 자신의 root계정으로 Connect test를 하는 단계가 있는데 이 과정까지 무사히 마치고 나면 MySQL설치는 완료가 됩니다! 

![spring-28](https://user-images.githubusercontent.com/42923027/104831904-3b85d300-58d0-11eb-930d-8e71b22cc03e.png)

---

설치가 완료되면 CMD창을 열고
```
mysql -u root -p 
```
명령어를 실행한 뒤 설치하면서 설정해준 root계정의 비밀번호를 입력하고 Enter!
그러면 아래와 같은 결과를 확인할 수 있습니다.

![spring-29](https://user-images.githubusercontent.com/42923027/104831930-81429b80-58d0-11eb-81a3-f695e01ec24d.png)


---



이번 포스트에서는 MySQL을 설치하는 과정을 다뤘습니다. 다음 포스트에서는 다시 스프링 프로젝트로 돌아가서 프로젝트와 MySQL Database를 연동하는 과정을 자세하게 다뤄보도록 하겠습니다.



