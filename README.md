![image](https://github.com/srsr47/disneylandproject/assets/101054398/feb39283-56e3-4e70-8685-e4d96444b75d)


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
* 데이터에 대한 소개 (링크) <br>
https://www.kaggle.com/datasets/arushchillar/disneyland-reviews  

### 기본적인 정보 : 어떠한 데이터인지, 총 데이터 건 수  
* 데이터 정보

|Review_ID|Rating|Year_Month|Review_Text|Location|
|------|---|---|---|---|
|각 리뷰에 부여된 고유 ID|평점|방문일자|방문자출신국가|코멘트|디즈니랜드 파크 위치| 
                                             
이 데이터에는 디즈니랜드 여러 지점들 중 거기서도 파리, 캘리포니아, 홍콩 총 3개 지점에 대한 트립어드바이저 방문자가 게시한 평점 등 총 42,000개의 리뷰가 있다. 
평점은 1(불만족)부터 5(만족)까지 구성되어 있다.

* 활용할 데이터 예시

  
| -     | Review_ID | Rating | Year_Month |    Reviewer_Location | Review_Text                                                                                        | Location            |
|-------|-----------|--------|------------|---------------------:|----------------------------------------------------------------------------------------------------|---------------------|
| 1     | 670772142 | 4      | Apr-19     | Australia            | "One of the rides  its a Small World  is absolutely fabulous..."                                   | Disneyland_HongKong |
| 2     | 670682799 | 4      | May-19     | Philippines          | "Bakery in Main Street now have more attractive..."                                                | Disneyland_HongKong |
| 3     | 670623270 | 4      | Apr-19     | United Arab Emirates | "Although I had an amazing time."                                                                  | Disneyland_HongKong |
| ...   |           |        |            |                      |                                                                                                    |                     |
| 42656 | 1645894   | 5      | missing    | South Africa         | "The highlight of our stay was the Walt Disney Studios."                                           | Dinseyland_Paris    |
| 42657 | 1618637   | 4      | missing    | United States        | "This hotel, part of the Disneyland Paris complex, is a wonderful place for families..."           | Dinseyland_Paris    |
| 42658 | 1536786   | 4      | missing    | United Kingdom       | "The minute you enter, the transport to disneyland paris, you are treated like a special guest..." | Dinseyland_Paris    |


### 2.2 추출한 데이터
대량의 데이터에서 관심 영역을 추출한다. (5만 ~ 10만건)<br>
*최소 2만건(파이참과 csv 파일 연결하기)  

<img width="990" alt="스크린샷 2024-04-28 130750" src="https://github.com/dltnfls/disneylandproject/assets/101054398/88a546ed-4c00-44e4-873c-c626b24d3a69">


### 2.3 추출한 데이터에 대한 탐색적 데이터 분석
* 1~5점 척도인 경우에는 분포

<img width="98" alt="image" src="https://github.com/dltnfls/disneylandproject/assets/101054398/1e12b4b5-9b56-4066-a193-e396cfcee41e">

* 리뷰 개수  

| 리뷰개수             |
|----------------------|
| 방문자가 남긴 코멘트 |
| 42632                |
| 고유한 값            |

* 방문한 디즈니랜드 지점 분포(Location별로 리뷰가 몇 건 있는지 bar plot을 통해 나타냈다.)<br>
  X축: 디즈니랜드 지점 <br>
  Y축: 리뷰의 수 <br>
  
![barplot](https://github.com/srsr47/disneylandproject/assets/101054398/3f82289f-4a0f-420f-9b79-64bfe5d6e4ed)

bar plot을 통해 California > Paris > HongKong 순으로 리뷰 수가 많음을 확인할 수 있다.

* 평점(1~5점)의 분포가 어떻게 되는지 bar plot으로 나타냈다.<br>
  X축: Rating(1,2,3,4,5 평점) <br>
  Y축: 리뷰의 수 <br>

![rating](https://github.com/srsr47/disneylandproject/assets/101054398/919f1a76-10f4-4d89-a6aa-64e9d5603519)

bar plot을 통해 5 > 4 > 3 > 2 > 1 순으로 리뷰의 수가 많음을 확인할 수 있다. 

* Year_Month에 따른 리뷰의 수 살펴보기
  수많은 리뷰들 중 대체로 사람들이 언제 많이 방문하여 작성했는지를 선 그래프로 표시하였다. <br>
  X축: 년도 <br>
  Y축: 리뷰의 수 <br>

![year_month](https://github.com/srsr47/disneylandproject/assets/101054398/7e485885-5772-43ca-bd96-dc130f58035b)

선 그래프의 결과, 대체로 2015년에서 2016년 사이에 가장 많은 사람들이 리뷰를 작성했음을 알 수 있다.


## 3. 학습 데이터 추출
### 3.1 Label로 분류
이번에는 csv 파일을 데이터 프레임으로 읽어와 새로운 데이터 프레임을 생성한 후, 
Review_Text를 통해 리뷰들을 긍정과 부정으로 분류해보기로 했다. <br>
먼저 csv 파일 속 필요없는 Review_ID를 삭제하고 Review_Text라는 열 이름을 Review로 바꾼 후, Review 길이가 20자 미만, 600자 이상인 데이터를 삭제하였다. <br>
Rating이 1점 또는 2점인 Review에는 '부정', Rating이 4점 또는 5점인 Review에는 '긍정' label을 부여하고 Rating이 3점인 Review는 삭제를 했다. <br>
'긍정'의 경우 1로 표시를, '부정'의 경우 0으로 표시를 했다. <br>
총 24155개의 결과가 나왔다.

| Number | Review                                            |Label|
|--------|---------------------------------------------------|-----|
| 1      | If you've ever been to Disneyland anywhere you... |  1  |
| 2      | HK Disneyland is a great coompact park.           |  1  |
| ...    | ...                                               |  ...|
| 24154  | I would not recommend going if you have been...   |  0  |
| 24155  | My eleven year old daughter and myself went to... |  0  |

[24155 rows x 3 columns]

### 3.2 긍부정에 대한 비율 
총 42,000개의 리뷰 중 24,155개를 뽑아 긍부정 비율을 원그래프로 나타낸 결과, 93.9%가 긍정적인 편이었고 나머지 6.1%가 부정적인 리뷰였다.

<img width="586" alt="24155label" src="https://github.com/srsr47/disneylandproject/assets/101054398/b7437318-0628-4d81-a025-7d1053e94d41">


### 3.3(1) 1500:1500(긍부정 비중)
3.1과 같은 방법으로 새로운 데이터셋을 생성하였다. 다만 원래는 긍정과 부정 각각 임의로 1500개씩 추출하여 최종 데이터셋을 생성하려고 했으나 부정적인 리뷰의 수가 1500개보다 적어 오류가 발생하였다. 이를 해결하기 위해 임의로 추출할 부정적인 리뷰의 수를 원본 데이터셋에서 가능한 최대값인 부정적인 리뷰의 수로 설정하였고 원본 데이터셋에서 부정적인 리뷰의 수를 확인하고 그 수를 기반으로 샘플링하도록 코드를 수정하였다. 

| Number | Review                                             |Label|
|--------|----------------------------------------------------|-----|
| 0      | We loved it.                                       |  1  |
| 1      | Show up when the park opens. The park is...        |  1  |
| 2      | My family visited Disney HK last october...        |  1  |
| 3      | What a fun couple days! Our family went to Dis...  |  1  |
| 4      | Visited Disney over the Christmas holidays...      |  1  |
| ...    | ...                                                | ... |
| 2979   | Far too many rides shut for renovations the...     |  0  |
| 2980   | This place hasn't changed in years. While the...   |  0  |
| 2981   | We went for one day and I have to say, it was...   |  0  |
| 2982   | We had a eurodisney holiday booked for me, my ...  |  0  |
| 2983   | A large proportion of the Disneyland Park is c...  |  0  |

[2984 rows x 3 columns]

### 3.3(2) 3,000건을 임의로 추출(긍부정 비중)
이번에는 임의로 3,000건을 추출하여 긍부정의 비중이 어떻게 되는지 만들어 보았다. 실행한 결과 긍정은 93.8%, 부정은 6.2%로 24,155개를 추출했을 때와 비슷하게 나타났다.

| Number | Review                                             | Label |
|--------|----------------------------------------------------|-------|
| 3286   | Excellent place is not only for Kids but for a...  | 1     |
| 14499  | Absolutely the best place for kids on the west...  | 1     |
| 4596   | I went here with a friend last month and had a...  | 1     |
| 5306   | Hong Kong Disneyland is very small. But...         | 1     |
| 8233   | All life's worries disappear when I go here. I...  | 1     |
| ...    | ...                                                | ...   |
| 5742   | Pros: Very beautiful, the mickey mouse thrain i... | 1     |
| 11576  | Having been a periodic visitor since 1957, I w...  | 1     |
| 3070   | This Disney park is the least interesting of a...  | 0     |
| 4653   | Disneyland HK had all the fun of the other Dis...  | 1     |

<img width="524" alt="3000random" src="https://github.com/srsr47/disneylandproject/assets/101054398/6d8b724c-61cd-4ad6-bdcd-1bc00fea89a5">


## 4. MobileBERT 학습 결과

## 5. 느낀점 및 배운점
csv 파일 하나로 이렇게 여러 결과들을 도출해내면서 한번에 볼 수 있다는 점이 편리하기도 했다.
하지만 정확도를 예측하기 위해 실행하는 데에 시간이 오래 걸리고 오류가 여러 번 떠서 몇 번을 바꾸는 데에도 시간이 오래 걸려서 좀 빠르게 실행될 수 있었으면 하는 아쉬움이 있었다.
