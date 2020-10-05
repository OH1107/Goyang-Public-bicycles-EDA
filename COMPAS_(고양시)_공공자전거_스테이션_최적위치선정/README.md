# COMPAS - 고양시 공공자전거 스테이션 최적위치 선정
- 본 공모전은 첫번째 프로젝트로 많은 시행착오를 겪으며 진행하였다.
- 같이 교육을 듣는 교육생들과 함께 공모전을 진행하며 EDA 과정을 목표로 진행하였다.
  - 당시 역량으로는 머신러닝, 딥러닝 알고리즘 개발이 불가능했다.
- 본 공모전은 실패한 공모전이다...(기대치에 미치지 못했다.)
## 개요
### 배경
- 고양시는 2010년부터 공공자전거 서비스([피프틴](https://www.fifteenlife.com))를 도입하여 약 161개 스테이션(자전거 보관소)과 1,700여대의 공공자전거로 시민들에게 서비스를 제공
- 현재 고양시는 신규 택지개발 등으로 도시화 지역이 늘어나고 인구 증가 등으로 인하여 기존 스테이션 위치에 대한 조정이 필요
### 목적
- 공공자전거 운영이력 데이터 및 공간 데이터를 활용하여 자전거 스테이션의 최적 위치를 선정하여 향후 시민들의 공공자전거(공유자전거) 사용에 대한 접근성을 개선
### 해결 과제
- 고양시에 대하여 공공자전거 스테이션의 최적위치를 제시
- 분석 조건
  - 스테이션의 개수는 최대 300개소
  - 스테이션별 자전거 수용 용량 최대 30대
### 참고
- 일정 및 결과제출 방법은 [COMPAS 홈페이지 참조](https://compas.lh.or.kr/subj/past/info?subjNo=SBJ_2007_001)
## 설명
- 인원 : 5명
- 작업툴 : `Python`, `Jupyter Notebook`, `Google Colab`, `QGIS`
- 사용 라이브러리 : `pandas`, `numpy`, `matplotlib`, `haersine`, `geojson`, `json`, `folium`, `shpely.geometry`
## 데이터
- [COMPAS에서 제공한 35종 데이터](https://github.com/OH1107/Project/tree/master/COMPAS_(%EA%B3%A0%EC%96%91%EC%8B%9C)_%EA%B3%B5%EA%B3%B5%EC%9E%90%EC%A0%84%EA%B1%B0_%EC%8A%A4%ED%85%8C%EC%9D%B4%EC%85%98_%EC%B5%9C%EC%A0%81%EC%9C%84%EC%B9%98%EC%84%A0%EC%A0%95/data)
---
## 프로그래밍
### 0. 환경
- COMPAS 홈페이지에서 제공하는 `Jupyter hub`를 사용했다.
### 1. 라이브러리 import 하기
#### 1-1. 필요 데이터 불러오기
![image](https://user-images.githubusercontent.com/67505208/93592106-8825d400-f9ec-11ea-9dd2-4274894cd877.png)
- 위의 방법은 COMPAS에서 제공하는 `Jupyter hub` 환경만의 방법으로 간편하게 데이터를 호출할 수 있다.
  - 예시
  ```python
  from geoband.API import *
  GetCompasData('SBJ_2007_001', '1', '01.운영이력.csv')
  ```
#### 1-2. 데이터 처리를 위한 패키지와 모듈 불러오기
![image](https://user-images.githubusercontent.com/67505208/93592362-008c9500-f9ed-11ea-9061-758372a3b12d.png)
### 2. 데이터 전처리
#### 2-1. 스테이션의 좌표값으로 구역값(구, 동) 부여
- '02.자전거스테이션.csv'의 위도와 경도 데이터
![image](https://user-images.githubusercontent.com/67505208/93592658-86104500-f9ed-11ea-8e55-0ce842bfc23a.png)
- '34.고양시_행정경계(행정동기준).geojson'의 geometry값(`MULTIPOLYGON` 형태이다.)
![image](https://user-images.githubusercontent.com/67505208/93592812-ca034a00-f9ed-11ea-96c0-6cf86f0c4b6c.png)
