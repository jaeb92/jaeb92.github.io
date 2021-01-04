---
title: "Jekyll로 Github 블로그 만들기 - (2) jekyll 테마 선택 및 github repository 연동"
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
<pre>추후 이 repository 이름을 URL창에 입력해서 블로그에 접속이 가능하다.</pre>

---
