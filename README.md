# disneylandproject
## Dinseyland 리뷰 분석 프로젝트  
<!-- 
badge icon 참고 사이트
https://github.com/danmadeira/simple-icon-badges
-->
<img src="https://img.shields.io/badge/python-%233776AB.svg?&style=for-the-badge&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/pytorch-%23EE4C2C.svg?&style=for-the-badge&logo=pytorch&logoColor=white" />
<img src="https://img.shields.io/badge/pycharm-%23000000.svg?&style=for-the-badge&logo=pycharm&logoColor=white" />

## 1. 개 요 A4용지로 1장정도 (그림포함)
### 1.1 디즈니랜드란?
디즈니랜드는 미국 캘리포니아주 애너하임에 위치한 월트 디즈니가 설립한 테마파크로, 디즈니 캐릭터와 디즈니 영화를 기반으로 한 다양한 놀이시설과 엔터테인먼트를 제공하는 곳이다. 원래는 1만 평의 단순한 공원으로 시작했지만, 후에 디즈니의 상상력과 창의성을 담은 테마파크로 발전했다.
현재는 미국뿐만 아니라 일본, 프랑스 등 여러 나라에도 생겼고, 가족이나 친구들과 함께 즐길 수 있는 인기 있는 관광지 중 하나이다.

### 1.2 문제 정의
2019년 중국에서부터 시작된 코로나로 인해 몇 년간 전 세계 사람들은 해외여행은 물론, 국내여행조차 다닐 수 없었다. 코로나가 점차 완화되고 백신 등 치료법들이 개발되면서 다시 전처럼 세계여행을 다닐 수 있게 되었다. 많은 관광지들 중 난 이번 프로젝트에서는 해외여행을 하려는 사람들을 위해 해외 곳곳에 있는 디즈니랜드를 다녀온 사람들의 반응을 분석해 보고자 한다.

## 2. 데이터
### 2.1 원시 데이터
데이터에 대한 소개 (링크)
https://www.kaggle.com/datasets/arushchillar/disneyland-reviews  

<br> 기본적인 정보 : 어떠한 데이터인지, 총 데이터 건 수  
<br> 데이터 정보


<img width="511" alt="image" src="https://github.com/dltnfls/disneylandproject/assets/101054398/5b601032-ab76-4f03-ae86-8ee54363d81b">


이 데이터에는 디즈니랜드 여러 지점들 중 거기서도 파리, 캘리포니아, 홍콩 총 3개 지점에 대한 트립어드바이저 방문자가 게시한 평점 등 총 42,000개의 리뷰가 있다. 
평점은 1(불만족)부터 5(만족)까지 구성되어 있다.

### 2.2 추출한 데이터
대량의 데이터에서 관심 영역을 추출한다. (5만 ~ 10만건)
최소 2만건

### 2.3 추출한 데이터에 대한 탐색적 데이터 분석
1~5점 척도인 경우에는 분포<br>

<img width="98" alt="image" src="https://github.com/dltnfls/disneylandproject/assets/101054398/1e12b4b5-9b56-4066-a193-e396cfcee41e">

<br> 리뷰 개수  

<img width="95" alt="image" src="https://github.com/dltnfls/disneylandproject/assets/101054398/b66e1560-9de5-4974-8d7d-120b2a2b899e">  

<br> 방문한 디즈니랜드 지점 분포

<img width="97" alt="image" src="https://github.com/dltnfls/disneylandproject/assets/101054398/c24fc444-f18d-4249-805c-0e4520a12442">

리뷰 문장의 길이
연도별, 장소별 등등 데이터의 부가정보를 바탕으로 데이터를 탐색 (pandas, matplotlib)

# 여기까지가 중간 과제 점검 

## 3. 학습 데이터 구축

## 4. MobileBERT 학습 결과

## 5. 느낀점 및 배운점
