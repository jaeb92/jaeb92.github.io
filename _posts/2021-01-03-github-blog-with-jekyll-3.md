---
title: "Jekyll로 Github 블로그 만들기 - (2) jekyll 테마 선택 및 github repository 연동"
layout: categories
permalink: /categories/
categories: Jekyll github 삽질
---

지난 포스트에서는 windows와 mac os에서 ruby 및 jekyll, bundler를 설치하는 방법을 알아봤다.

이번 포스트에서는 jekyll 테마를 선택해서 자신의 github repository와 연동하는 방법을 알아보도록 하자.

---

<h3>1) 자신이 원하는 테마 선택하기</h3>
- <ol>https://github.com/topics/jekyll-theme</ol>
위의 링크를 타고 들어가서 자신이 원하는 테마를 선택한다. 

나는 best match로 정렬방식을 선택해서 가장 먼저 나오는 **minimal-mistakes** 테마로 선택했다.
###### 테마는 취향대로! but, 테마마다 적용 방식은 다를 수도 있다. <br/> 테마 별 자세한 방식은 테마 제작자가 적어둔 매뉴얼을 참고하자.

![스크린샷 2021-01-04 22 24 13](https://user-images.githubusercontent.com/42923027/103539563-aa7c2880-4edb-11eb-8650-30a870b7f175.png)

---

<h3>2) 원하는 테마의 repository를 fork 하기</h3>
  
저 테마를 클릭하면 테마의 repository로 접근할 수 있다.
repository로 들어간 후 페이지 우측 상단에 Fork 버튼을 눌러서 자신의 repository로 fork를 진행하자.
![스크린샷 2021-01-04 22 30 07](https://user-images.githubusercontent.com/42923027/103540053-6f2e2980-4edc-11eb-92e0-4f8121fa9262.png)

---

<h3>3) 자신의 username으로 repository 이름 변경하기</h3>

fork가 완료된 자신의 repository의 settings로 들어가서 repository이름을 다음과 같이 변경해주자.
내 username은 'jaeb92'이다 그래서 **jaeb92.github.io**가 내 repository 이름이 된다.
<pre>이 repository 이름을 url창에 입력해서 <br/> 블로그로 이동할 예정</pre>

![스크린샷 2021-01-04 22 49 44](https://user-images.githubusercontent.com/42923027/103541715-2d52b280-4edf-11eb-95a5-849a256f9d4e.png)

---
fork를 하고 repository이름을 변경하고 나면 아래와 같은 화면을 볼 수 있을 것이다.

![스크린샷 2021-01-04 22 54 56](https://user-images.githubusercontent.com/42923027/103542262-0a74ce00-4ee0-11eb-81ae-f3ac8822708e.png)


---


<h3>4) 자신의 local 환경에 repository clone 받기 </h3>

위에서 생성한 자신의 repository를 clone받자.


아래의 주소를 복사!

![스크린샷 2021-01-04 23 00 06](https://user-images.githubusercontent.com/42923027/103542687-a56da800-4ee0-11eb-81e1-8ebeeeb454e2.png)


windows의 command창이나 mac os의 terminal을 실행. <br>clone 받고자 하는 경로로 이동한 뒤 다음의 명령어를 실행!
(mac os는 기본적으로 git이 세팅되어 있어 바로 실행가능하지만 windows의 경우에는 git을 별도의 설치를 진행해야 한다.)

*참고로 필자는 mac os를 사용하고 있다.*
~~~ 
> git clone https://github.com/jaeb92/jaeb92.github.io

Cloning into 'jaeb92.github.io'...
remote: Enumerating objects: 36, done.
remote: Counting objects: 100% (36/36), done.
remote: Compressing objects: 100% (24/24), done.
remote: Total 18145 (delta 24), reused 24 (delta 12), pack-reused 18109
Receiving objects: 100% (18145/18145), 43.72 MiB | 8.35 MiB/s, done.
Resolving deltas: 100% (10849/10849), done.
~~~

자신의 local환경에 clone까지 되었다면 초기 세팅과정은 마무리가 다 되어간다고 본다.<br>이제는 **jekyll 테마별 개인 설정**을 진행해야 하는데 이 부분은 테마별로 <br>설정하는 방법이 조금씩 다를 수 있으니 처음에 말했던 것처럼 **<br>테마 저작자가 만들어둔 매뉴얼을 참고하여 진행하는 것을 추천한다.**



