---
title: "Jekyll로 Github 블로그 만들기 - (1) 환경설정 & 삽질"
categories: Jekyll github 삽질
---

Github블로그를 만들어보기로 결심을 하고 여기저기 구글링을 해봤다. 역시 갓글!

여러 포스트들을 떠돌아 다녀본 결과 github 블로그를 만드는 방법은 2가지 정도로 가능한 것 같다.
그 중에 내가 진행한 한 가지 방법을 소개하겠다.

우선 Jekyll은 ruby라는 언어로 만들어졌기 때문에 ruby를 먼저 설치를 하고 진행해야 한다.
블로그 하나 하려고 Ruby와 그와 관련한 모듈들을 설치하려니.. 부담이 좀 되긴 했는데 어쩌겠나..  
다 내가 하고자 했는데.... 어쨌든..

[MAC OS] 설치방법은 다음과 같다.
1. brew install rbenv   
<img width="268" alt="스크린샷 2021-01-03 16 31 20" src="https://user-images.githubusercontent.com/42923027/103474354-63603b80-4de6-11eb-8ca4-5d4859a03843.png">

2. vim ~/.zshrc 실행  
  
3. [[ -d ~/.rbenv ]] && \
    export PATH=${HOME}/.rbenv/bin:${PATH} && \
  eval “$(rbenv init -)” 추가 작성 후 저장
<img src="../assets/img/스크린샷 2021-01-03 16.58.13.png" width="300" height="60"> 
