---
title: "Hadoop 한번 해보기 (1) - Map Reduce가 뭐죠? Map? 🗺 지도인가요🤣🤣?"
categories: Hadoop
---

# 1. Map Reduce? 
<h4><center> 맵리듀스의 맵이 그 🗺 맵인가요??</center></h4>
<h3><center>아닙니다.😗</center></h3>
<h4><center>그럼 뭐죠?</center></h4>
<br>

<center>Map-Reduce는 대용량의 데이터를 처리하기 위해 2004년에 구글에서 발표한 소프트웨어 프레임워크다.</center>
<center>(출처: 위키백과)</center>


<h3><center>위키백과에 잘 나와 있네요. 지금까지 글 읽어주셔서 감사합니다. 🙋‍♂️ </center></h3>
<br>
<h3><center>농담입니다🤦‍♂️</center></h3>
<br>

<h4><center>저도 배워가는 입장이기 때문에 정보전달의 느낌이 아니라</center>
<center><h3>'제가 알고 있는 게 맞나요?'</h3>의 느낌으로 적어보도록 하겠습니다.</center>
<br>
<center>틀린 부분들 과감히 지적해주시면</center>
<center>그 지적... 달게 받겠습니다.</center>
<center>🍦🍭🍬🍩</center></h4>

<br>
<center><h4>맵리듀스의 핵심 내용은 이렇습니다.</h4></center>
<center>대용량의 데이터를 클러스터링 환경으로 분산시켜 병렬적으로 처리될 수 있도록 하는 것.</center>
<center>즉, 하나의 컴퓨터에서 모든 데이터들을 다루는 것이 아니라 여러 대의 컴퓨터에 데이터들을 분산시켜서 저장하고 처리하도록 하는 것입니다.</center>
<center><h4>생활 속 간단한 비유를 들어드리겠습니다.</h4></center>
<center>2마트, 집더하기.. 이런 느낌의 대형마트들을 가보면 많은 사람들이 쇼핑을 하고 계산하기 위해 여러 캐셔 앞에 줄을 서 있는 모습을 흔히 볼 수 있습니다.</center>
<br>
<center><h4>만약... 그 많은 사람들이 한 명의 캐셔에게 줄을 서서 계산을 한다면?? 😖😫🤬</h4></center>


<center><h4>🙈상상도 하기 싫습니다.🙈</h4></center>


<center>마트 안의 모든 손님을 한 명의 캐셔가 계산한다면 캐셔도 돌아버리고 기다리는 손님들도 돌아버리고 대환장파티가 벌어질 건 뻔하네요... </center>
<center>완벽한 비유는 아니지만 느낌적인 느낌을 봐주시기 바랍니다 ㅎㅎ</center>

<center><h4>이렇듯 한 컴퓨터에 엄청난 양의 데이터를 몰아주지 않고 여러 컴퓨터가 각자 정해진 데이터의 양을 맡아서 처리하게 하는 거죠</h4></center>


<pre><center><h4>한 컴퓨터한테 너무 많은 데이터를 몰아주지 마세요.</h4></center>  
<center><h4>☠️🤖그 컴퓨터... 어떻게 변할지 모릅니다... 🤖☠️</h4></center>
<center>

<iframe src="https://giphy.com/embed/ZrJcTENQacGhW" width="350" height="350" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>
<h5>🥶😱 도망쳐 😱🥶</h5>
</center>
</pre>

<br>
<center>하지만 </center>
<center>여러 컴퓨터에 데이터를 나누어 처리하는 게</center>
<center>무조건적으로 좋다고는 할 수 없습니다.</center>
<center>하나의 컴퓨터가 모든 데이터를 처리하는 것보다</center>
<center>여러 대의 컴퓨터가 동일한 데이터의 양을 처리하는 것이</center>
<center>당연히 처리 속도는 훨씬 증가하겠죠?</center> 
<center>하지만 그에 따른 부작용도 역시 존재합니다.</center>
<br>
<center><h3>하나의 예를 들어보겠습니다.</h3></center>
<center>단 하나의 옷장에 모든 옷들을 넣어두게 되면</center>
<center>어떤 옷을 어디에 넣어야 되는지 고민할 필요가 없죠.</center>
<br>
<center>그냥 그 옷장을 열어서 모든 옷을 뒤져보면</center>
<center><h4>언젠간</h4></center>
<center>자신이 원하는 옷을 찾아낼 수 있을 겁니다</center>
<center><h5>(언제가 될지 장담할 수 없습니다  🤪)</h5></center>
<center>
<iframe src="https://giphy.com/embed/m0J6AoVwSD3mU" width="350" height="360" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>
</center>


<br>

<center><h4>그렇지 않다면?</h4></center>
<center>어떤 공간에 어떤 옷, 어떤 신발들을 넣어놔야 하는지..</center>
<center>고민이 많이 될 수가 있죠. </center>
<center><iframe src="https://giphy.com/embed/CxWPp7VYuYURa" width="350" height="360" frameBorder="0" class="giphy-embed" allowFullScreen></iframe></center>
<center><h4>🤔 어떤 데이터를 어느 저장소에 넣어야 하지 🤔? </h4></center>
<center><h4>🤔 내가 찾는 데이터가 어느 저장소에 있지 🤔? </h4></center>

<center>이런 구조적인 것을 설계하는 단계부터 더 복잡해지게 되는 것이죠</center>
<br>

~~<center>😎 이래서 설계가 중요합니다 😎</center>~~
<br><br>


<center>

<h3>조금 더 자세하게 적어보겠습니다 🙋‍♂️</h3>

<br>
<center>맵 리듀스는 크게 맵(Map)과 리듀스(Reduce)의 단계를 거치게 됩니다.</center>
<center>중간에 여러 단계들도 존재하긴 합니다만</center>
<center>이번 포스트에서는 맵과 리듀스에 집중해보도록 하겠습니다.</center>
<br>


<center><b>맵(Map)</b>이라는 단계에서는</center>
<center>대용량의 데이터를 </center>
<center>잘개 쪼개고</center>
<center>서로 연관있는 데이터들을 분류하는</center>
<center>일련의 과정을 수행하는 것입니다.</center>
<br>

<center><b>리듀스(Recude)</b>라는 과정에서는</center>
<center>이전 과정까지 거쳐온 데이터들 중에</center>
<center>자신이 원하는 데이터를 추출하는 과정입니다.</center>


<center><h1>🧑‍💻</h1></center>

