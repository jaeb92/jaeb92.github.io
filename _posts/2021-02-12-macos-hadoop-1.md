---
title: "MAC OS Hadoop 설치하고 테스트해보기 (1) - 설치 및 환경설정"
categories: Hadoop
---

# 1. Hadoop이란?

하둡(Hadoop)이란 대용량 데이터를 분산하여 처리할 수 있는 자바 기반 오픈소스 프레임워크이다. RDB로는 수 테라 또는 그 훨씬 이상의 데이터를 다루기에는 쉽지 않아 개발되었다고 한다.


하나의 컴퓨터에서 데이터를 처리하는 것이 아니라 여러 대의 컴퓨터를 클러스터링하여 각 컴퓨터에서 대용량의 데이터들을 병렬적으로 처리할 수 있도록 하여 처리 속도를 증가 시킨다.


# 2. brew로 hadoop 설치하기

<pre><code>$ brew install hadoop</code></pre>

brew로 hadoop 설치하다가 아래와 같은 에러가 발생할 수 있다.

> Error: The brew link step did not complete successfully. The formula built, but is not symlinked into /usr/local. Could not symlink sbin/FederationStateStore. /usr/local/sbin is not writable."

<code>mkdir /usr/local/sbin </code> 경로를 생성해준 뒤 다시 진행하자.