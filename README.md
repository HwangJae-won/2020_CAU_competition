# 2020 제 1회 CAU 응용통계학과 분석 공모전

# 1. 개요
- 주제: TV 프로그램이 골목 상권에 미치는 영향 분석 및 예측
- 수상: 우수상 (16개 팀 중 3위)
- 기간: 2020.09 ~ 2020.11
- 팀원: 김성관, 박준근, 정서연, 황재원
- 사용 skill: Python, R

<img width="1232" alt="스크린샷 2021-11-03 오후 1 51 29" src="https://user-images.githubusercontent.com/79994991/140011472-e40ee2e1-63eb-47f2-9dfe-98cbf55d7dda.png">

# 2. 데이터 전처리 
- Raw Data
  - 공공데이터 (서울시 열린 데이터 광장)
    - 서울시 우리마을가게 상권분석서비스(상권-추정매출) (https://data.seoul.go.kr/dataList/OA-15572/S/1/datasetView.do)
    - 서울시 우리마을가게 상권분석서비스(상권-추정유동인구) (https://data.seoul.go.kr/dataList/OA-15568/S/1/datasetView.do)    
  - 크롤링: 골목식당 식당 상권별 출현 회차 크롤링
- 추정 매출 및 유동인구 데이터 상권별로 정리한 후 데이터 보정 진행: 데이터 수집 방식 변화에 따른 보정 (데이터 수급처 감소), 코로나 영향에 따른 보정
<img width="1168" alt="image" src="https://user-images.githubusercontent.com/79994991/167239953-3f7f2848-ade4-4338-8482-25b0f0644f3b.png">
- 매출과 매출 건수에 영향을 줄거라 예상되는 변수 추가: 시청률, 방송 여부, 분기

# 3. 분석 및 예측
## 3-1) Regression fitting
- 골목 식당에 출연한 상권들 중 각 상권이 원래 가지고 있는 트렌드를 고려하여 골목식당의 방영이 매출액과 매출건수에 영향이 있는지 확인
- 방송 전의 매출액, 매출건수 데이터들을 이용하여 회귀직선을 그린 후에 추정된 회귀 계수들을 통해 방송 분기 혹은 방송 후 분기를 예측하고 실제 데이터와 비교하였고, 그 결과가 예측한 결과보다 실제가 크다면 방송의 효과가 있다고 판단

## 3-2) 상도동 상권 분석
- 감정 분석 진행 : 시청자의 반응에 따라 매출액 및 매출 건수가 다를 것이라 예상하여 공식 영상의 댓글 크롤링하여 감성 분석 진행
- 감성 분석 결과 점수(긍정 리뷰/(긍정 리뷰 + 부정 리뷰))를 변수로 추가하여 예측에 활용
<img width="585" alt="image" src="https://user-images.githubusercontent.com/79994991/167249033-0413d129-149a-4cbe-85f6-304844b31588.png">
- R을 활용한 변수 선택 및  multiple regression 시행
<img width="581" alt="image" src="https://user-images.githubusercontent.com/79994991/167249091-a691f67e-2d35-4db2-a616-90f9661a01de.png">

# 4. 결론
<img width="576" alt="image" src="https://user-images.githubusercontent.com/79994991/167249101-c2312253-9a9f-48ab-8ec1-c5b2a4f82314.png">

