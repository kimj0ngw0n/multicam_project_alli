# 여름철 아이들 물놀이장 정보 제공 서비스


## 목차

1. 소개
    1. 웹 동작 시연 및 설명
1. 기획
    1. 주제 선정 배경
    1. 타겟층
    1. 주요 기능
1. 데이터
    1. 데이터 수집
    1. 데이터 전처리
1. 데이터 분석
    1. 편의지수
    1. 시각화
    1. 리뷰 긍/부정 감성분석
    1. 리뷰 키워드 추출
1. 클라우드
1. 웹 개발
1. 확장 가능성
1. 후기
1. 기타(데이터 출처)


## 1. 소개

- 목적 : 여름철 아이들과 함께 갈 수 있는 물놀이장에 대한 정보를 제공하는 웹 사이트를 만든다.

- 팀원 : 김종원(데이터 분석, 백엔드), 김지우(데이터 분석, 백엔드), 신건우(클라우드, 프론트엔드)

- 사용 언어 및 툴

    > 데이터 분석 : Python, R<br>
    웹 개발 : Django, React<br>
    클라우드 환경 : AWS<br>
    DB : MySQL<br>
    협업 : 구글 드라이브, 디스코드, Zoom, Notion

- 소요 기간 : 5주


### 웹 동작 시연 및 설명

#### 1. 시연 영상

- 용량 문제로 영상을 2개로 나누고 5배속을 적용했다.

    [1번 시연](https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/2258e529-e7c8-4a7d-ba76-d7b1868c1613)

    [2번 시연](https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/cb389aec-972b-436d-9d1c-82b259280988)

#### 2. 동작 설명

시연 영상을 중심으로 설명했으며, 점수 도출 방식 등의 자세한 내용은 목차 이후에서 확인할 수 있다.

<div align="center">메인 페이지</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/431ab5a8-7228-4a5a-993a-0cc9f4763fd2">

> 메인 페이지에서 사용자와 물놀이장, 바닥분수, 야외수영장(이하 편의상 세 가지 시설 모두 물놀이장이라 한다)의 위치를 확인할 수 있다.<br>
왼쪽의 토글 버튼을 클릭하면, 아래와 같이 편의시설의 위치를 확인할 수 있는 버튼들이 나타난다.

<div align="center">편의시설 토글 활성화</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/b4c5e24a-a495-4db0-af5f-575cc7b9ff40">

> 활성화된 버튼들을 클릭하면 해당 편의시설의 위치를 보여준다.<br>
예를 들어 약국 버튼을 클릭하면 해당 시설의 위치가 표시된다.

<div align="center">팝업 창 활성화</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/d9a1de83-bddc-4899-83b7-29f300205bcb">

> 물놀이장 아이콘을 클릭하면 팝업 창이 활성화 된다.<br>
팝업 창에는 물놀이장의 기본적인 정보와 상세페이지, 길찾기 버튼이 있다.

<div align="center">상세페이지 활성화 1</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/173dc46a-5179-46d6-be75-087b137e887a">

<div align="center">상세페이지 활성화 2</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/c7657424-6bdf-48ea-9b98-7a15ab942af5">

> 기본적으로 물놀이장의 사진, 상세 정보를 제공한다.<br>
추가적으로 물놀이장의 편의지수, 리뷰 긍정부정비율, 물놀이장의 상세 편의지수, 행정구역 내 평균 편의지수와의 비교, 리뷰 워드클라우드를 제공한다.

<div align="center">통계 한눈에 보기 페이지</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/65e7df57-6070-48f5-addc-34eadd82b3a4">

> 위쪽 사이드 바에서 '통계 한눈에 보기' 버튼을 클린하면,<br>
편의지수가 가장 높은 TOP 5 물놀이장, 전체 물놀이장 리뷰 워드클라우드, 행정구역 별 물놀이장 편의지수 평균 그래프, 행정구역 별 물놀이장 편의지수 평균 시각화 자료가 제공된다.


## 2. 기획

### 1. 주제 선정 배경

서울특별시에서는 매년 여름 바닥분수와 물놀이장 등을 가동한다.<br>
또한 키워드 검색량 증가율을 찾아본 결과, 2023년 8월 6일 기준 월간 검색량은 60,600건에 달했고, 여름철에 물놀이장을 검색하는 횟수가 지속해서 증가 추이를 보인다.<br>
또한 서울 물놀이장을 검색했을 때, 여름철에 아이들과 함께 갈만한 물놀이장에 대한 수요가 매우 높은 것을 확인할 수 있다.

<div align="center">통계 한눈에 보기 페이지</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/86623a27-ed61-4913-9e11-c3c646102948">

> 이렇게 물놀이장 정보에 대한 수요는 높지만, 정보의 접근성은 매우 낮은 실정이다. 행정구역 별 사이트도 다 다르고, 필요한 정보를 얻을 수 없는 경우도 많다.

이런 불편함을 줄이고, 편의성을 높이기 위해서 '여름철 아이들 물놀이장 정보 제공 서비스'를 기획했다.


### 2. 타겟층

- 3~10세의 자녀를 둔 부모 또는 보호자를 타겟으로 한다.


### 3. 주요 기능

- 물놀이장, 편의시설들의 위치 및 정보 제공

- 물놀이장에 대해 편의지수 시각화

- 리뷰 데이터 분석 결과 시각화


## 3. 데이터

주요 데이터들은 아래와 같다.


### 1. 데이터 수집

물놀이장

- 서울특별시 내 물놀이장 3종류에 대한 rawdata 수집

- 위도 및 경도 데이터가 포함되어 있는 편의시설 10종류에 대한 rawdata 수집

편의지수

- 인덱스 도출 관련 선행 연구 논문 수집

- 물놀이장 데이터 전처리를 통해 거리 데이터 확보

리뷰

- 물놀이장에 대한 구글 맵 리뷰 크롤링

<div align="center">데이터 리스트 및 예시</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/8dac1d99-6470-4b8b-bf7a-f3fac871114f">

> 순서대로 서비스에 사용된 데이터 리스트, 물놀이장 raw data 예시, 물놀이장 데이터를 Data Frame으로 변형한 결과이다.


### 2. 데이터 전처리

결측치 제거 및 데이터 정제

물놀이장과 편의시설의 좌표 사이의 거리를 계산하여 파생변수 추가

- 좌표와 좌표 사이의 거리를 계산하는 하버사인 공식 응용

편의시설 종류 별 만족거리 및 시설별 민감도(K)에 대해 회귀분석을 통해 새로운 민감도(K) 계산

<div align="center">물놀이장과 편의시설 사이의 거리 예시(단위 : m)</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/a2a6f553-955f-44c8-9d76-d6b6bf4f1b24">


## 4. 데이터 분석

### 1. 편의지수

<div align="center">노선가식 평가방법의 접근계수와 Aoyama Research Model</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/dee49ab2-3b03-4834-b3b3-5d348b9a6ae4">

위의 두 그래프들은 각각 '노선가식 평가방법의 접근계수'와 'Aoyama Research Model'(이하 아오야마 모형)이다.

이 모델들이 시사하는 점은 아래와 같다.

> 개인이 시설을 이용함으로써 얻는 가치는 해당 시설 서비스의 이용가치와 이동으로 잃는 가치의 차이로 나타난다.<br>
이 가치가 0 이하가 될 때, 이론적으로 시설은 장점을 잃어 이용하지 않게 된다.

예시) 편의점

- 어떤 편의점이 물놀이장 기준 1km 밖에 있다면, 그 편의점은 굳이 이용하지 않을 것이다.
- 물놀이장과 편의점 사이의 거리가 너무 멀어서, 편의점을 이용함으로써 얻는 가치보다 이동으로 잃는 가치가 더 크기 때문이다.

이 때, 효용가치가 0이 되기까지 한계 거리, 단위거리 당 심리적 부담 등을 구하기 위해 아오야마 모형을 토대로 편의시설 접근성을 연구한 선행 논문을 분석했다.

<div align="center">최정민, 박동찬 (2020), '주거환경 생활편의시설의 접근성 및 중요도에 관한 연구'</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/df766760-60cf-43af-ac90-340f8389a4d0">

해당 논문에서는 20대에서 50대까지 2250명을 대상으로 설문조사를 진행하여, 각종 편의시설에 대한 만족거리 평균값과 k 값을 구했다.<br>
이 때, 만족거리와 k 값의 의미는 아래와 같다.

- 만족거리는 해당 논문에서 접근거리라고도 언급하며, 연구가설을 위한 조작적 정의이다.

> 만족거리 : 시설로부터 멀어질수록 이용자의 시설 만족도라는 효용이 떨어져 불만을 일으키게 되기까지의 거리

> k : 시설의 만족거리에 따른 민감도. 값이 작을수록 거리가 멀어짐에 따라 만족도가 급격하게 감소함

예시) 대형 마트와 편의점의 비교

- 대형 마트의 경우, 거리가 조금 멀더라도 사람들은 큰 불만없이 시설을 방문한다.
- 편의점의 경우, 거리가 조금만 멀어도 사람들의 불만이 커진다.
- 따라서 대형 마트에 비해 편의점의 만족거리와 k 값이 작다.

우리는 이 설문조사 데이터를 참고하여 서비스가 제공하는 편의시설들에 대한 만족거리와 k 값 산정의 근거로 활용했다.

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/e3cb5c0f-16a8-4205-a9f4-105af9c2d67f">

본 서비스는 아이들이 이용하는 물놀이장에 대한 정보를 제공한다.<br>
따라서 주차장과 수유실 및 어린이 이용가능 화장실(이하 수유실 또는 화장실)의 만족거리를 어린이 보행속도를 고려하여 위와 같이 각각 600m, 300m로 정했다.

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/6bf43933-8dd5-4ace-9952-3cfe5a1458b5">

만족거리와 k 값의 변화를 산점도로 그려본 결과, 선형 회귀 모형을 따르는 것을 확인할 수 있었다. 

따라서 우리 서비스에 맞게 새롭게 정한 만족거리에 해당하는 k 값을 우측 표와 같이 예측하고 사용했다.

또한, 아오야마 모형에서 $\lambda$가 커질수록 편의시설로부터 얻는 서비스 가치가 작아져야 하므로 k 값의 역수를 사용했다.

위 근거들을 바탕으로 아래와 같은 순서에 따라 편의지수를 도출했다.

1. 물놀이장 1개와 편의시설 1개에 대한 개별 점수 도출 후 합산
2. 각 편의시설 별 점수 정규화 $\times$ 시설별 민감도(계수)
3. 모든 물놀이장에 대한 점수 도출 후 표준점수화


### 2. 시각화

<div align="center">편의지수 시각화 예시</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/f708da85-c56e-4a48-965e-aa65a907282f">

구해진 물놀이장의 편의지수를 범주화했다. 편의지수 '상/중/하'를 각각 파랑/노랑/빨강 계열의 마커 색깔로 나타내어, 해당 물놀이장의 마커의 색깔만 확인해도 편의지수 등급을 확인할 수 있도록 했다.

<div align="center">물놀이장 1개의 편의지수 시각화 예시</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/d8d7e499-2af9-4988-9b73-447297969c6b">

상세페이지에서 해당 물놀이장이 구체적으로 어떤 편의시설에 대한 편의지수가 높은지를 방사형 차트를 활용해 나타냈다.<br>
이를 통해 사용자가 중요하게 생각하는 편의시설에 대해 파악하기 용이하다.

이외에도 웹 동작 설명란에서 보았던 '통계 한눈에 보기' 페이지에 나타나 있는 편의지수가 가장 높은 TOP 5 물놀이장, 전체 물놀이장 리뷰 워드클라우드, 행정구역 별 물놀이장 편의지수 평균 그래프, 행정구역 별 물놀이장 편의지수 평균 시각화 자료가 제공된다.


### 3. 리뷰 긍/부정 감성분석

<div align="center">물놀이장에 대한 구글 맵 리뷰 예시</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/c5b7a6f8-45a1-4f8b-9839-ef5a61f28f7f">

구글 맵에서 물놀이장에 대한 리뷰를 크롤링하고, KoNLPy의 Okt 모델을 통해 형태소 분석과 토큰화를 했다.<br>
토큰화된 리뷰를 딥러닝 모델에 적용하여 긍정적인 리뷰인지, 부정적인 리뷰인지 판별했다. 은닉층과 출력층은 아래와 같다.

> 은닉층 : LSTM<br>
출력층 : Sigmoid

<div align="center">리뷰 긍/부정 판별 예시</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/3e20a1ba-86a3-4c56-a4b8-1362e8733dd7">

<div align="center">리뷰 긍/부정 판별 후 점수 시각화</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/cb74e794-73cf-4b3d-8511-7d75f9894c17">

판별된 리뷰의 비율을 계산하여 상세페이지에서 위와 같이 시각화했다.


### 4. 리뷰 키워드 추출

마찬가지로 KoNLPy의 Okt 모델을 활용하여 명사를 추출했다. 너무 낮은 빈도의 키워드는 제외하고, 사용자의 니즈에 맞춰 불용어 처리를 통해 아이, 공원, 물놀이 등의 키워드는 삭제했다.

<div align="center">리뷰의 키워드를 워드클라우드로 시각화</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/f28623c9-5df9-4f79-b706-c164ca1d1fe9">

위와 같이 상세페이지에서 해당 물놀이장 리뷰의 키워드들을 추출하여 워드클라우드로 시각화했다.


## 5. 클라우드

<div align="center">인프라 설계 구성도</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/62d8cf1d-e1c8-4166-bb37-ee2e9f9fc6ae">

클라우드는 2개의 가용영역(Availability zone)으로 나누어져 있다. 각 가용영역 public subnet에는 리액트를 배포할 ec2와 rds 관리를 위한 bastion host로 구성되어 있고, private subnet에는 장고서버를 배포할 2개의 ec2와 rds로 구성되어 있다. 사용자는 1번을 통해 웹사이트의 화면을 전달받고 2번을 통해 데이터 분석 및 AI 딥러닝 결과를 axios 형태로 호출한다.

> 클라우드 부분은 데이터의 흐름 정도만 이해한 상태이다. 인프라 설계부터 구축에 이르기까지 이해가 비교적 완벽하지 않다.


## 6. 웹 개발

<div align="center">ERD 구성도</div>

<p align="center"><img src="https://github.com/kimj0ngw0n/multicam_project_alli/assets/127815502/47d85820-418f-4a29-bcaf-ff96303226e7">

DB는 MySQL을 사용했고, 빨갛게 강조 표시된 물놀이장 장소 테이블과 각 편의시설 별 데이터 테이블 사이에 '거리 테이블'을 생성하여 각 테이블을 연결해줬다.<br>
그 외 기능 구현을 위해 북마크, 리뷰, 유저 테이블을 만들어 관계를 설정했다.


## 7. 확장 가능성

아래는 시간, 기술 또는 데이터 부족으로 인해 실제로 구현하지 못한 부분이다.

1. 서비스의 개인화, 맞춤 서비스

    - 유저에게 편의시설 중요도를 선택할 수 있도록 개인화 맞춤 서비스 제공할 수 있다.
    - 만족거리 또는 k 값 설정을 통해 구현한다.

2. 리뷰 키워드의 긍정/부정 구분

    - 리뷰 키워드를 워드클라우드로 나타낼 때, 긍정적 또는 부정적인 키워드의 경우, 적절한 색깔을 부여하여 시각화 할 수 있다.

3. 추가 설문조사 실시

    - 직접 설문조사를 통해 만족거리와 k 값에 대한 신뢰도를 확보한다.

4. 제공 장소 범위 확대

    - 물놀이장, 바닥분수, 야외수영장에 한정된 서비스 범위를 넓혀 계곡과 해수욕장까지 확장 가능할 것이다.

5. 서비스 지역 확대

    - 현재 서울특별시만 서비스 되고 있지만, 후에 전국으로 확장 가능할 것이다.

6. 사용자 로그 기반 추천 서비스

    - 유저의 평점/리뷰 데이터와 북마크 한 장소 데이터를 기반으로 코사인 유사도 등을 통한 여름철 물놀이 장소 추천 서비스를 제공할 수 있을 것이다.


## 8. 후기

> 여러 과정을 배운 사람들이 모여 프로젝트를 진행했다. 이에 따라 여러 언어와 툴을 사용했으며, 작업이 명확하게 구분되지 않는 경우가 많았다.<br>
너무나 부족한 나의 실력은 항상 발목을 잡았다.<br>
금방 끝날줄 알았던 기획과 데이터 수집은 해도해도 결론이 나지 않고, 끝이 나지 않았다. 시간이 지체되어 마음이 급했고, 실제로 시간도 촉박했다.<br>
처음엔 쉽게만 생각했던 편의지수는 프로젝트를 진행하면 진행할수록 사막에서 바늘 찾는 것처럼 답이 없다고 느꼈다.

> 하지만 계속 공부해가며 여러 언어 및 툴에 적응했고, 실력 부족을 해결해나갔다.<br>
시간이 촉박해질 때까지 계속된 기획 검토와 최대한 많은 양의 데이터 수집은 결국 우리 프로젝트에 이롭게 작용했고,<br>
팀원과 함께 고민하여 결국 사막에서 바늘을 찾아냈다.

> 지금까지 진행했던 프로젝트에서 얻은 기획과 데이터의 중요성을 잊지 않았고, 팀원과 함께 끝까지 포기하지 않아 해냈다고 생각한다.<br>
다시 한 번 팀원분들께 감사드린다.


## 9. 기타(데이터 출처)

데이터 출처

- 서울 열린 데이터 광장
- 문화 빅데이터 플랫폼
- 스마트 서울맵
- 네이버 데이터랩
- 블랙키위
- 구글 지도

참고문헌

- 최정민·박동찬 (2020), '주거환경 생활편의시설의 접근성 및 중요도에 관한 연구'
- 김도형·김민경·박예린·박유민·황호영 (2021), '개인 맞춤형 부동산 추천 웹 서비스'

API 

- 카카오맵
