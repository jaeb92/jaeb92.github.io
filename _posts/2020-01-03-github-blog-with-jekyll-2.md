---
title: "Jekyll로 Github 블로그 만들기 - (1) ruby 및 사전준비"
categories: Jekyll github 삽질
---

Github블로그를 만들어보기로 결심을 하고 여기저기 구글링을 해봤다.

여러 포스트들을 떠돌아 다녀본 결과 github 블로그를 만드는 방법은 2가지 정도로 가능한 것 같다.
그 중에 내가 진행한 한 가지 방법을 소개하겠다.

우선 Jekyll은 ruby라는 언어로 만들어졌기 때문에 ruby를 먼저 설치를 하고 진행해야 한다.
블로그 하나 하려고 Ruby와 그와 관련한 모듈들을 설치하려니.. 부담이 좀 되긴 했는데 어쩌겠나..  
다 내가 하고자 했는데.... 어쨌든..


### [MAC OS] 에서 ruby 설치방법은 다음과 같다.


#### 1. brew로 rbenv 설치 
ruby를 설치하는 데에는 여러 방법이 있겠지만 이번엔 rbenv라는 써드파티를 이용하여 ruby 설치를 진행하였다.
- <pre>brew install rbenv   </pre>
<ol><img width="268" alt="스크린샷 2021-01-03 16 31 20" src="https://user-images.githubusercontent.com/42923027/103474354-63603b80-4de6-11eb-8ca4-5d4859a03843.png"> 
</ol>

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

### 3. ruby 설치 (2.7.2 버전)
- <pre> rbenv install 2.7.2 </pre>

### 4. 환경변수 설정  
  - vim ~/.zshrc  
  - [[ -d ~/.rbenv ]] && \  
         export PATH=${HOME}/.rbenv/bin:${PATH} && \  
         eval “$(rbenv init -)”  
    
    추가 작성 후 저장
  
<ol><img width="370" alt="스크린샷 2021-01-03 16 58 13" src="https://user-images.githubusercontent.com/42923027/103474387-a5897d00-4de6-11eb-88f9-b97b628093a2.png">
</ol>

### 5. 루비 설치 확인
  - <pre>ruby -v </pre>
  
  
<ol><img width="475" alt="스크린샷 2021-01-03 17 19 31" src="https://user-images.githubusercontent.com/42923027/103474508-f3eb4b80-4de7-11eb-958d-a2fb303671f5.png">
</ol>

위와 같이 버전이 잘 뜨면 설치가 아무 문제없이(?) 잘 마무리 된 것이다.


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


이상 jekyll을 이용한 github 블로그 만들기 첫 번째 단계를 마치고 다음 포스트부터는
본격적으로 jekyll 테마 설정방법과, github repository 연결하는 방법 등을 진행하도록 한다.


