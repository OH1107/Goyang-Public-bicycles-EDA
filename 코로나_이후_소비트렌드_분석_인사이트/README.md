# 코로나 이후 소비트렌드 분석 인사이트

## 개요
### 배경
- **소비트렌드 코리아2020**
  - KDX 한국데이터거래소에서 제공하는 데이터를 활용한 유통,소비데이터 & 시각화경진대회
### 목적
- 언택트, 뉴노멀 시대와 더불어 코로나 바이러스 발생 이후 급변하는 소비 행태를 분석 및 시각화를 실시
- 이를 바탕으로 2020년 코로나 이후 소비트렌드 제시 및 향후 소비 행태 인사이트 도출을 목표로 함
### 참고
- [KDX 한국데이터거래소](https://lab.kdx.kr/adl/contest/main.php)

## 설명
- 작업툴 : `Jupyter Notebook`, `Google Colab`, `Power BI`
- 사용 라이브러리 : `pandas`, `numpy`, `scipy`, `matplotlib`, `seaborn`
- 인원 : 5명
- 기간 : 2020.10.05 ~ 2020.10.16
- 담당 업무 : 팀장으로서 프로젝트 전반적인 기획업무, 인사이트 도출을 위한 필요 데이터 전처리 및 시각화

### 분석방향
- 상세 기입 필요
## 데이터
- 분석환경 내 제공 데이터
  - MBN : *매일경제 뉴스데이터*
  - 엠코퍼레이션 : *금융사 데이터를 기반으로 한 온라인 상품 구매 데이터*
  - 삼성카드 : *오프라인 상품 구매 데이터*
  - 신한카드 : *오프라인 상품 구매 데이터*
  - 지인플러스 : *전국 아파트 시세 및 거래량 데이터*
  - KDX : *무료데이터*
- 기타 활용 가능 데이터
  - 공공데이터 : *공공 데이터명 및 링크 표시*
  - 법적 문제없는 크롤링 데이터 : *크롤링 코드 필수*
## 결과
- 프로젝트 결과 : 장려상 (2020.11.05 80팀 중 4등)
- 프로젝트 결과물 : [최종 분석보고서](https://github.com/OH1107/Project/blob/master/%EC%BD%94%EB%A1%9C%EB%82%98_%EC%9D%B4%ED%9B%84_%EC%86%8C%EB%B9%84%ED%8A%B8%EB%A0%8C%EB%93%9C_%EB%B6%84%EC%84%9D_%EC%9D%B8%EC%82%AC%EC%9D%B4%ED%8A%B8/%E1%84%8F%E1%85%A9%E1%84%85%E1%85%A9%E1%84%82%E1%85%A1_%E1%84%8B%E1%85%B5%E1%84%92%E1%85%AE_%E1%84%89%E1%85%A9%E1%84%87%E1%85%B5%E1%84%90%E1%85%B3%E1%84%85%E1%85%A6%E1%86%AB%E1%84%83%E1%85%B3_%E1%84%87%E1%85%AE%E1%86%AB%E1%84%89%E1%85%A5%E1%86%A8_%E1%84%8B%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%90%E1%85%B3.pdf), [제출용 소스코드](https://github.com/OH1107/Project/blob/master/%EC%BD%94%EB%A1%9C%EB%82%98_%EC%9D%B4%ED%9B%84_%EC%86%8C%EB%B9%84%ED%8A%B8%EB%A0%8C%EB%93%9C_%EB%B6%84%EC%84%9D_%EC%9D%B8%EC%82%AC%EC%9D%B4%ED%8A%B8/final_analysis.ipynb)
---
## 프로그래밍
- 필요한 라이브러리 및 모듈을 호출한다.

![image](https://user-images.githubusercontent.com/67505208/100179813-1f8e3280-2f1a-11eb-9079-9b852b055ee8.png)

- 데이터 전처리를 진행하도록 한다.
  - 전처리에 앞서 어떤 데이터를 사용하는지 먼저 확인하고자 한다.

- 제공된 데이터 중 삼성카드, 신한카드 데이터 셋으로 **오프라인 상품 구매 이력**을 분석하고자 한다.
  - 그러나 삼성카드와 신한카드의 **업종별 범주**가 상이하므로 통일시키는 과정을 먼저 진행하고자 한다.
  
![image](https://user-images.githubusercontent.com/67505208/100180133-e30f0680-2f1a-11eb-88c4-bf19d152d5f7.png)

![image](https://user-images.githubusercontent.com/67505208/100180184-f7530380-2f1a-11eb-929a-aa270f35c55d.png)

- 삼성카드 데이터 형태

![image](https://user-images.githubusercontent.com/67505208/100336808-f654cb80-3019-11eb-8cf9-cb9081b57d7a.png)

- 신한카드 데이터와 삼성카드 데이터 통일화 작업 수행

![image](https://user-images.githubusercontent.com/67505208/100336953-20a68900-301a-11eb-93d8-0307ca3fe7de.png)

![image](https://user-images.githubusercontent.com/67505208/100337044-416ede80-301a-11eb-9f50-3b28ca66b30e.png)

- 데이터 컬렴명과 형태를 통일시킨 후 데이터 병합

![image](https://user-images.githubusercontent.com/67505208/100337206-6f542300-301a-11eb-8b76-87165d03fff9.png)

