---
title: "MAC OS Hadoop 설치하고 테스트해보기 (1) - 설치 및 환경설정"
categories: Hadoop
---

# 1. Hadoop이란?

하둡(Hadoop)이란 대용량 데이터를 분산하여 처리할 수 있는 자바 기반 오픈소스 프레임워크이다. RDB로는 수 테라 또는 그 훨씬 이상의 데이터를 다루기에는 쉽지 않아 개발되었다고 한다.


하나의 컴퓨터에서 데이터를 처리하는 것이 아니라 여러 대의 컴퓨터를 클러스터링하여 각 컴퓨터에서 대용량의 데이터들을 병렬적으로 처리할 수 있도록 하여 처리 속도를 증가 시킨다.


# 2. brew로 hadoop 설치하기

하둡은 자바 기반의 프레임워크이기 때문에 기본적으로 JDK가 설치되어 있어야 한다. 

나는 3.3.0버전의 하둡을 설치했는데 아래 링크를 타고 들어가면 하둡버전에 맞는 JDK가 필요하다고 안내된 것을 확인할 수 있다. 다음을 참고하여 jdk를 미리 설치해두자.


[Java verion for Hadoop](https://cwiki.apache.org/confluence/display/HADOOP/Hadoop+Java+Versions 'java version for hadoop')

<img width="653" alt="스크린샷 2021-02-12 14 28 29" src="https://user-images.githubusercontent.com/42923027/107733552-a2b36d80-6d3e-11eb-955a-45c6e6a5f4dc.png">



<pre><code>$ brew install hadoop</code></pre>

brew로 hadoop 설치하다가 아래와 같은 에러가 발생할 수 있다.

> Error: The brew link step did not complete successfully. The formula built, but is not symlinked into /usr/local. Could not symlink sbin/FederationStateStore. /usr/local/sbin is not writable."

<pre><code>$ mkdir /usr/local/sbin</code></pre> 
명령어를 실행하여 경로를 생성해준 뒤 다시 진행하자.


# 3. 환경설정

brew로 하둡이 정상적으로 설치되었다면 몇 가지 환경설정을 해주어야 한다.

<code>/usr/local/Cellar/hadoop/x.x.x(version)/libexec/etc/hadoop</code>
이 디렉토리 안에 

- hadoop-env.sh
- core-site.xml
- mapred-site.xml
- hdfs-site.xml

네 개의 파일을 수정해주도록 한다.

#### 1) hadoop-env.sh

이 파일을 에디터로 열어보면 정체불명의 설정내용들이 적혀있을 것이다. 가볍게 다 무시해주고 

<pre><code>export HADOOP_OPTS="$HADOOP_OPTS -Djava.net.preferIPv4Stack=true"</code></pre>

이렇게 적힌 코드라인을 찾은 뒤에 아래처럼 수정해준다.


<pre><code>export HADOOP_OPTS="$HADOOP_OPTS -Djava.net.preferIPv4Stack=true -Djava.security.krb5.realm= -Djava.security.krb5.kdc="</code></pre>


#### 2) core-site.xml
이 파일을 열면 하단에 보면 <configuration></configuration>이라고 되어 있는 부분에 아무런 내용이 없는 것을 확인할 수 있다. 이 안에 다음과 같이 수정해주자.

```
<configuration>
    <property>
      <name>hadoop.tmp.dir</name>
      <value>/usr/local/Cellar/hadoop/hdfs/tmp</value>
      <description>A base for other temporary directories.</description>
    </property>
    <property>
      <name>fs.default.name</name>
      <value>hdfs://localhost:9000</value>
    </property>
</configuration>
```


#### 3) mapred-site.xml
이 파일도 아래와 같이 수정해주자.

```
<configuration>
    <property>
        <name>mapred.job.tracker</name>
        <value>localhost:9010</value>
    </property>
</configuration>

```


#### 4) hdfs-site.xml
역시 다음과 같이 수정하자.

```
<configuration>
    <property>
        <name>dfs.replication</name>
        <value>1</value>
    </property>
</configuration>
```


# 4. hdfs 포맷
위의 네 개의 파일을 모두 수정하였으면 hdfs를 포맷해주자.

<pre><code>$ hdfs namenode -format</code></pre>

# 5. SSH key 생성

<pre><code>$ ssh-keygen -t rsa
$ cat ~/.ssh_id_rsa.pub >> ~/.ssh/authorized_keys</code></pre>

keygen을 할 때 key의 이름과 비밀번호를 입력하는 라인이 있는데 공백으로 엔터키를 눌러 진행하자.


# 6. 서비스 실행 / 중단

<pre><code>/usr/local/Cellar/hadoop/x.x.x/sbin</code></pre>
경로 안에 들어가보면 .sh파일들을 비롯해서 많은 파일들이 있는 것을 확인할 수 있는데 이 중에 
start-dfs.sh 파일로 하둡서비스를 실행할 수 있고 stop-dfs.sh파일로 하둡서비스를 중지시킬 수 있다.


<pre><code>$ /usr/local/Cellar/hadoop/x.x.x/sbin/start-dfs.sh ----> 서비스 시작</code></pre>
<pre><code>$ /usr/local/Cellar/hadoop/x.x.x/sbin/stop-dfs.sh  ----> 서비스 중지</code></pre>
 

# 7. 서비스 실행 시 경고발생(Warning)

서비스를 실행하면 아래와 같은 경고가 발생할 수 있다.
```
WARN util.NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable
```

다른 블로그들을 참조한 결과 이는 하둡서비스를 실행하는데 큰 문제는 없는 경고라고 한다. 그래도 매번 실행할 때마다 이런 경고가 뜨면 눈에 거슬리니까 우선 해결하고 지나가자.

**3. 환경설정**을 하면서 수정해준 네 개의 파일중에 **hadoop-env.sh** 파일을 열어서 다음을 추가해준다.

```
$HADOOP_HOME/lib/native
export HADOOP_OPTS="$HADOOP_OPTS -Djava.library.path=$HADOOP_PREFIX/lib/native"
```


# 8. 샘플데이터 dfs에 추가해보기

<pre><code>$ touch hadoop_sample.txt</code></pre>
빈 파일을 생성해준다.

<pre><code>$ hdfs dfs -put hadoop_sample.txt</code></pre>

위의 명령어를 수행하면 dfs에 생성해준 hadoop_sample.txt파일이 이동한다.

이 때 아래와 같은 에러가 발생할 수 있다. 
```
ls: `.': No such file or directory
```

나의 경우에는 hdfs://localhost:9000/user/(사용자이름)의 경로가 없어서 나는 에러였다.

아래의 명령어를 실행하여 해당 디렉토리를 생성해준 뒤에 다시 put 해보자.
<pre><code>$ hdfs dfs -mkdir -p /user/(사용자이름) </code></pre>


<pre><code>$ hdfs dfs -ls </code></pre>
명령어를 실행하면 해당 파일이 잘 들어가 있는지 확인할 수 있다.



