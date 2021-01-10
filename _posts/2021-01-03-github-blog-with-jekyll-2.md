---
title: "Jekyll로 Github 블로그 만들기 - (1) ruby 설치 및 사전준비"
layout: categories
permalink: /categories/Jekyll/
categories: Jekyll
---

Github블로그를 만들어보기로 결심을 하고 여기저기 구글링을 해봤다.

여러 포스트들을 떠돌아 다녀본 결과 github 블로그를 만드는 방법은 2가지 정도로 가능한 것 같다.
그 중에 내가 진행한 한 가지 방법을 소개하겠다.

우선 Jekyll은 ruby라는 언어로 만들어졌기 때문에 ruby를 먼저 설치를 하고 진행해야 한다.
블로그 하나 하려고 Ruby와 그와 관련한 모듈들을 설치하려니.. 부담이 좀 되긴 했는데 어쩌겠나..  
다 내가 하고자 했는데.... 어쨌든..

## [Windows OS]에서 ruby 설치방법은 다음과 같다.
windows에서 뭘(개발) 하다보면 exe파일로 간단하게 설치하고 설치 마지막에 PATH설정도 바로 해주는 경우가 있어서 편하긴하다.

---

### 1. ruby 공식 홈페이지에서 다운로드
- https://www.ruby-lang.org/ko/downloads/ 로 이동하여 자신의 os 환경에 맞게 다운로드를 진행한다.

저 새빨간 **Download** 버튼을 누르면 친절하게 버전을 추천해주고 있다.
<ol>
  <img width="850" alt="스크린샷 2021-01-03 16 31 20" src="https://user-images.githubusercontent.com/42923027/103477883-53f0ea80-4e06-11eb-8f61-e908c4be7130.png"> 
</ol>


---


- 추천해주는 대로 **Ruby+Devkit 2.7.2-1 (x64)** 을 클릭하여 installer를 다운로드 한다.
<ol>
  <img width="850" alt="스크린샷 2021-01-03 16 31 20" src="https://user-images.githubusercontent.com/42923027/103477921-91ee0e80-4e06-11eb-99ee-c1b0edcef3c9.png"> 
</ol>

---

### 2. 다운받은 파일로 인스톨을 진행한다. 

인스톨을 진행하면서 나타나는 창 모두 next를 진행하면 되는데 주의할 부분은 다음이다.


![ruby-2](https://user-images.githubusercontent.com/42923027/103478151-fb225180-4e07-11eb-8bf0-4d0d4873e5d4.png)

 

## PATH를 설정하는 부분을 꼭 체크하고 넘어가도록 하자. 

안 그러면 직접 시스템설정에 들어가서 추가하는 번거로운 과정을 거쳐야 한다. 
남은 과정은 모두 NEXT를 눌러 무사히 마치도록 한다.


---


### 3. 루비 설치 확인

경로체크까지 하고 설치를 마무리 헀다면 COMMAND 창을 열자.

- <pre> ruby -v </pre>

위의 명령어를 실행했을 때 루비가 정상적으로 설치되고 경로까지 설정되어 있다면 아래와 같이 자신이 설치한 버전을 확인할 수 있다.

![ruby-2-3](https://user-images.githubusercontent.com/42923027/103478283-cc58ab00-4e08-11eb-899f-63fb3cb42971.png)


루비까지 정상적으로 설치가 된 것을 확인한 뒤

- <pre> gem install jekyll bundler </pre>


명령어를 실행하여 jekyll과 bundler를 설치해주자.


정상적으로 설치가 됐다면 아래와 같은 로그를 확인할 수 있다.


![ruby-2-4](https://user-images.githubusercontent.com/42923027/103478309-1b9edb80-4e09-11eb-921f-05fb678f384a.png)

이상 window에서 ruby, jekyll, bundler설치과정을 알아보고 다음은 MAC OS에서의 과정이다.


---


## [MAC OS] 에서 ruby 설치방법은 다음과 같다.

---


#### 1. brew로 rbenv 설치 
ruby를 설치하는 데에는 여러 방법이 있겠지만 이번엔 rbenv라는 써드파티를 이용하여 ruby 설치를 진행하였다.
- <pre>brew install rbenv   </pre>
<ol><img width="268" alt="스크린샷 2021-01-03 16 31 20" src="https://user-images.githubusercontent.com/42923027/103474354-63603b80-4de6-11eb-8ca4-5d4859a03843.png"> 
</ol>

---

### 2. rbenv로 설치 가능한 루비버전 확인
- <pre> rbenv install -l </pre>
<pre>2.5.8
2.6.6
2.7.2
3.0.0
jruby-9.2.14.0
mruby-2.1.2
rbx-5.0
truffleruby-20.3.0
truffleruby+graalvm-20.3.0
</pre>

---

### 3. ruby 설치 (2.7.2 버전)
- <pre> rbenv install 2.7.2 </pre>

---

### 4. 환경변수 설정  
  - vim ~/.zshrc  
  - [[ -d ~/.rbenv ]] && \  
         export PATH=${HOME}/.rbenv/bin:${PATH} && \  
         eval “$(rbenv init -)”  
    
    추가 작성 후 저장
  
<ol>
  <img width="370" alt="스크린샷 2021-01-03 16 58 13" src="https://user-images.githubusercontent.com/42923027/103474387-a5897d00-4de6-11eb-88f9-b97b628093a2.png">
</ol>

---

### 5. 루비 설치 확인
  - <pre>ruby -v </pre>
  
  
<ol><img width="475" alt="스크린샷 2021-01-03 17 19 31" src="https://user-images.githubusercontent.com/42923027/103474508-f3eb4b80-4de7-11eb-958d-a2fb303671f5.png">
</ol>

위와 같이 버전이 잘 뜨면 설치가 아무 문제없이(?) 잘 마무리 된 것이다.

---

루비가 정상적으로 설치가 됐다면 다음엔 jekyll, bundler을 설치해보자

- <pre>gem install jekyll bundler</pre> 


다음과 같은 로그가 찍히면 정상적으로 설치가 완료된 것이다.

<pre>Successfully installed jekyll-4.2.0
Parsing documentation for jekyll-4.2.0
Done installing documentation for jekyll after 0 seconds
Successfully installed bundler-2.2.4
Parsing documentation for bundler-2.2.4
Done installing documentation for bundler after 1 seconds
2 gems installed
</pre>

---

이상 jekyll을 이용한 github 블로그 만들기 첫 번째 단계를 마치고 다음 포스트부터는
본격적으로 jekyll 테마 설정방법과, github repository 연결하는 방법 등을 진행하도록 한다.


