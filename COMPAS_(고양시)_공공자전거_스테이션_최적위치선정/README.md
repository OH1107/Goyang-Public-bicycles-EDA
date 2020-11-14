# COMPAS - 고양시 공공자전거 스테이션 최적위치 선정
- 본 공모전은 첫번째 프로젝트로 많은 시행착오를 겪으며 진행하였다.
- 같이 교육을 듣는 교육생들과 함께 공모전을 진행하며 EDA 과정을 목표로 진행하였다.
  - 당시 역량으로는 머신러닝, 딥러닝 알고리즘 개발이 불가능했다.
- 본 공모전은 실패한 공모전이다...(기대치에 미치지 못했다.)
  - 스테이션 최적 위치 추가하는 과정에 있어 많은 논리적 개요가 부족
    - 대여량과 반납량이 비슷하다는 점을 통해 '이용량'으로 묶어 분석을 진행 -> 실제 대여/반납량과 차이가 존재할 것
    - 인구 증가에 따른 스테이션 추가 : 증가율에 따른 효율적 배치가 아닌 '인구가 증가한 지역이라면 스테이션 배치'
    - 효율적 배치를 위해서는 사용량이 적은 스테이션을 제거했어야 하나 그러지 못함
  - 첫 프로젝트인만큼 시간 분배를 적절히 하지 못해, 빠듯하게 분석을 진행하였음
    - 그만큼 프로젝트의 완성도 또한 
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
- 사용언어 : `Python`
- 작업툴 : `Jupyter Notebook`, `Google Colab`, `QGIS`
- 사용 라이브러리 : `pandas`, `numpy`, `matplotlib`, `haersine`, `geojson`, `json`, `folium`, `shpely.geometry`
- 인원 : 5명
- 기간 : 2020.07.28 ~ 2020.09.11
- 담당 업무 : 

### 분석 방향
- 현재 고양시 공공자전거(이하 피프틴)는 __여가 활동, 출퇴근/등하교의 목적으로 가장 많이 이용한다.__
![image](https://user-images.githubusercontent.com/67505208/98527927-f6856500-22be-11eb-8775-db91d1cf83c5.png)
- 또한 **신도시계획에 따라 인구가 점점 증가하는 추세**이며, 이에 따라 피프틴의 이용량도 증가할 것이다.
![image](https://user-images.githubusercontent.com/67505208/98528046-1b79d800-22bf-11eb-90da-0fd91fca7571.png)
- 그렇기에 **기존 피프틴 이용 목적**과 최근 **고양시 인구 증가 및 사회 변화**에 따라 **다음 3가지의 요소**로 신규 스테이션 위치 선정을 진행하고자 한다.
  - __출퇴근/등하교 목적__
    - 출퇴근/등하교 시간대의 이용량을 분석하여 이용밀도가 높은 지역의 추가 스테이션 설치
    - 주거 지구, 상업 지구, 학교를 중심으로 
  - __여가 활동 목적__
    - 주말동안의 대여/반납 이용량을 분석하여 이용밀도가 높은 지역의 추가 스테이션 설치
    - 주로 체육 시설과 같은 공공 여가 시설의 위치를 확인하며 진행
  - __사회 변화 대응__
    - 도시 계획 진행을 고려한 추가 스테이션 배치
    - 인구 통계 데이터를 기반으로 증가율을 반영

## 데이터
- [COMPAS에서 제공한 35종 데이터](https://github.com/OH1107/Project/tree/master/COMPAS_(%EA%B3%A0%EC%96%91%EC%8B%9C)_%EA%B3%B5%EA%B3%B5%EC%9E%90%EC%A0%84%EA%B1%B0_%EC%8A%A4%ED%85%8C%EC%9D%B4%EC%85%98_%EC%B5%9C%EC%A0%81%EC%9C%84%EC%B9%98%EC%84%A0%EC%A0%95/data)

![image](https://user-images.githubusercontent.com/67505208/99145236-607f7f00-26b0-11eb-8f21-78fb08a37a1c.png)

## 결과
- 프로젝트 결과 : **참가상** (2020.09.23 18팀 중 9등)
- 프로젝트 결과물 : [최종 분석보고서](https://github.com/OH1107/Project/blob/master/COMPAS_(%EA%B3%A0%EC%96%91%EC%8B%9C)_%EA%B3%B5%EA%B3%B5%EC%9E%90%EC%A0%84%EA%B1%B0_%EC%8A%A4%ED%85%8C%EC%9D%B4%EC%85%98_%EC%B5%9C%EC%A0%81%EC%9C%84%EC%B9%98%EC%84%A0%EC%A0%95/submission/%ED%94%BC%ED%94%84%ED%8B%B4%EC%9D%84%ED%83%84%EB%AC%B8%EB%8F%8C%EC%9D%B4_%EB%B6%84%EC%84%9D%EB%B3%B4%EA%B3%A0%EC%84%9C.pdf), [제출용 소스코드](https://github.com/OH1107/Project/blob/master/COMPAS_(%EA%B3%A0%EC%96%91%EC%8B%9C)_%EA%B3%B5%EA%B3%B5%EC%9E%90%EC%A0%84%EA%B1%B0_%EC%8A%A4%ED%85%8C%EC%9D%B4%EC%85%98_%EC%B5%9C%EC%A0%81%EC%9C%84%EC%B9%98%EC%84%A0%EC%A0%95/submission/%ED%94%BC%ED%94%84%ED%8B%B4%EC%9D%84%ED%83%84%EB%AC%B8%EB%8F%8C%EC%9D%B4_%EC%86%8C%EC%8A%A4%EC%BD%94%EB%93%9C.ipynb)
---
## 프로그래밍
- COMPAS 홈페이지에서 제공하는 `Jupyter hub`를 사용했다.

- 분석에 필요한 5가지의 데이터를 호출하도록 한다. 
![image](https://user-images.githubusercontent.com/67505208/93592106-8825d400-f9ec-11ea-9dd2-4274894cd877.png)
- 위의 방법은 COMPAS에서 제공하는 `Jupyter hub` 환경만의 방법으로 간편하게 데이터를 호출할 수 있다.
  - 예시
  ```python
  from geoband.API import *
  GetCompasData('SBJ_2007_001', '1', '01.운영이력.csv')
  ```
- 데이터 처리를 위한 패키지와 모듈 불러온다.
![image](https://user-images.githubusercontent.com/67505208/93592362-008c9500-f9ed-11ea-9061-758372a3b12d.png)

- 데이터 형태를 먼저 확인해보도록 한다.
  - '02.자전거스테이션.csv'의 위도와 경도 데이터
![image](https://user-images.githubusercontent.com/67505208/93592658-86104500-f9ed-11ea-8e55-0ce842bfc23a.png)
  - '34.고양시_행정경계(행정동기준).geojson'의 geometry값(`MULTIPOLYGON` 형태이다.)
![image](https://user-images.githubusercontent.com/67505208/93592812-ca034a00-f9ed-11ea-96c0-6cf86f0c4b6c.png)

- 해당 Station별 위도와 경도 좌표를 통해 어떤 동에 위치하고 있는지 알아보고자 한다.
![스크린샷 2020-11-09 오후 6 12 20](https://user-images.githubusercontent.com/67505208/98521728-2a5c8c80-22b7-11eb-80a1-9fa30ee1c08d.png)

- '02.자전거스테이션.csv'에 'dong'이라는 컬럼으로 병합시켜 위치값을 추가한다.
![스크린샷 2020-11-09 오후 6 14 58](https://user-images.githubusercontent.com/67505208/98522032-8b846000-22b7-11eb-980f-695b3da9d39c.png)

### 동별 주말/평일 이용량 TOP 10 선별

- 그럼 이제 이떤 동의 스테이션이 반납과 대여가 활발한지 알아보고자 한다. 그에 앞서 대여, 반납 정보가 포함되어 있는 '01.운영이력.csv' 데이터를 확인해본다.

  | LEAS_NO | LEAS_STAT | LEAS_DATE | LEAS_STATION | LEAS_DEF_NO | RTN_DATE | RTN_STATION | RTN_DEF_NO | TRNV_QTY | MEMB_DIV | MEMB_NO | TEMP_MEMB_NO | BIKE_TAG | RTN_PROCESS
-- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | --
15945541 | 2 | 2017-01-01 00:00:41 | 213 | 18 | 2017-01-01 00:13:52 | 260 | 17 | 0.0 | 6 | 164203 | 0.0 | 1A844000000BB7 | NaN
15945542 | 2 | 2017-01-01 00:01:03 | 231 | 4 | 2017-01-01 00:50:24 | 231 | 17 | 31039.0 | 1 | 187551 | 0.0 | 1A844000000494 | NaN
15945543 | 2 | 2017-01-01 00:01:50 | 119 | 14 | 2017-01-01 01:01:50 | 0 | 0 | NaN | 12 | 168994 | 0.0 | 1A844000000533 | 1.0
15945544 | 2 | 2017-01-01 00:02:09 | 121 | 17 | 2017-01-01 00:15:58 | 133 | 14 | 15490.0 | 12 | 183971 | 0.0 | 1A844000000731 | NaN
15945545 | 2 | 2017-01-01 00:03:32 | 320 | 29 | 2017-01-01 00:18:44 | 259 | 27 | 0.0 | 12 | 167475 | 0.0 | 1A84400000F343 | NaN

- 월별 사용량을 알아보기 위해 대여, 반납 일시를 월별로 추출하도록한다.
![image](https://user-images.githubusercontent.com/67505208/98522544-2bda8480-22b8-11eb-99e5-4bf1a1840969.png)

- 또한 주최측에서 제시한 이상치에 대한 처리를 하도록한다.
  - 반납 스테이션이 '0, 999, 998, 992'는 내부 확인용 혹은 분실 수리를 위한 별도 관리 ID
  ![image](https://user-images.githubusercontent.com/67505208/98522843-82e05980-22b8-11eb-9735-9c2ac985f77c.png)
  
- 대여량과 반냡량을 카운트하여 최고 빈도수 즉, 사용이 활발한 스테이션을 확인해보도록 한다.

![image](https://user-images.githubusercontent.com/67505208/98523064-ce930300-22b8-11eb-99eb-6396bcf4d2b9.png)

![image](https://user-images.githubusercontent.com/67505208/98523132-e66a8700-22b8-11eb-81ad-6cdb275176cc.png)

![image](https://user-images.githubusercontent.com/67505208/98523257-0a2dcd00-22b9-11eb-82d7-f8808ce50e97.png)

![image](https://user-images.githubusercontent.com/67505208/98523223-00a46500-22b9-11eb-9d11-bf4982501597.png)

- __대여, 반납이 많은 순으로 정렬했을때, 스테이션의 등수가 대부분 동일한 것을 볼 수 있다.__

### 동별 출퇴근/등하교 이용량 TOP 10 선별
- 앞서 진행했던 전처리 과정대로 스테이션별 대여, 반납 위치(행정동)을 추가한다.

![image](https://user-images.githubusercontent.com/67505208/98662702-87c20d80-238b-11eb-86d1-42326653c19d.png)

![image](https://user-images.githubusercontent.com/67505208/98662748-96102980-238b-11eb-928f-22747a1e76e6.png)

- '01.운영이력.csv'데이터로부터 요일별 사용량을 추출한다.

![image](https://user-images.githubusercontent.com/67505208/98662921-c6f05e80-238b-11eb-8210-4a1ad1120b98.png)

- 출퇴근 시간대를 파악하기 위해 평일동안의 사용량(대여,반납)을 시간별로 확인해본다.
  - 평일 대여량
  ![image](https://user-images.githubusercontent.com/67505208/98664050-37e44600-238d-11eb-8b4b-ef82634b8b88.png)
  - 평일 반납량
  ![image](https://user-images.githubusercontent.com/67505208/98816199-a4ce0d80-246b-11eb-972a-3484d4c87cf4.png)
  - __대여량과 반납량의 차이가 크지 않으므로 대여량=이용량으로 가정하여 분석 진행__
  
- 평일 시간대별 이용량을 통해 스테이션에 자전거 공급과 배분이 적절하게 이뤄지는지 파악해보고자 한다.
  - 하루 평균 해당 동 스테이션 이용량
![image](https://user-images.githubusercontent.com/67505208/98816323-d8109c80-246b-11eb-970c-60285f083c38.png)

- 출퇴근시간을 따로 추출하여 하루 평균 해당 시간대의 대여량을 확인하고자 한다.
  - 출근시간(06시-09시 59분), 퇴근시간(17시-20시25분)으로 가정
  ![image](https://user-images.githubusercontent.com/67505208/98817233-27a39800-246d-11eb-9ab1-0dfc17bffdcc.png)

- 출퇴근시간대에 임의의 스테이션에서 자전거를 대여하고자하는데 자전거가 없는 경우도 발생할 수 있다.
  - 스테이션에 거치되어 있는 자전거 수를 안다면 어떤 스테이션에서 위 문제가 발생하는지 알 수 있을 것이다.
  
- 다음의 보고서를 참고하여 실제 거치되어 있는 자전거의 수는 거치대 수량에 31%만큼 배치한 다는 것을 알 수 있다.
![스크린샷 2020-11-11 오후 10 32 52](https://user-images.githubusercontent.com/67505208/98817701-dd6ee680-246d-11eb-96fe-2ed7c4b8bc0a.png)
  - 실제 배치되어 있을 자전거 수 예측
  
  ![image](https://user-images.githubusercontent.com/67505208/98817807-08f1d100-246e-11eb-8e9f-0fe5bc7a8c5a.png)

- 배치되어 있는 예측 자전거 수와 실제 하루 평균 사용량 간의 차이 파악
  - 이때 '배치되어 있는 자전거 수' - '출퇴근 사용량' 값이 음수 값을 띈다면 앞서 언급한 **문제가 발생**하는 것이다.
    - 출근 시간대에 대여하고 싶지만 자전거가 없는 상황 -> 추가 배치가 필요한 상황이다.

    ![image](https://user-images.githubusercontent.com/67505208/98818571-18bde500-246f-11eb-9371-3bd6e41f326b.png)

- 이제 츨근 시간대의 이용량과 퇴근 시간대의 이용량 별로 정렬하여 자전거 배치가 필요한 동을 알아보고자 한다.
  - 출근 이용량 TOP 10
  
  ![image](https://user-images.githubusercontent.com/67505208/98818765-57539f80-246f-11eb-97fd-ec4d3e71aa2e.png)
  - 퇴근 이용량 TOP 10
  
  ![image](https://user-images.githubusercontent.com/67505208/98818828-6d616000-246f-11eb-9083-1eaab4f5fb6e.png)

### 동별 인구수 증가 지역 TOP 10 선별
- 인구수가 증가하는 지역을 알아보도록 한다.
- '07.인구통계.csv'데이터 먼저 확인 해보도록한다.

![image](https://user-images.githubusercontent.com/67505208/99068886-a5dc7780-25f0-11eb-9a4b-b27cfdd6c0f7.png)

- '총인구수' 컬럼의 값들을 숫자로 연산하기 위해 ','를 제외 처리를 한다.
- 또한 동이름을 통일하기위한 전처리를 실시한다.

- 동별 인구수 증감량을 확인하기 위해 '2017년 1월'과 '2019년 12월'의 값의 차이를 구한다.
- 인구수 증가가 많이된 순으로 정렬하여 동을 확인하도록 한다.

![image](https://user-images.githubusercontent.com/67505208/99069112-15526700-25f1-11eb-9671-9acaffe2090e.png)

### 신규 스테이션 추가 대상 지역
- 분석 방향에 언급한 3가지 기준에 대해서 스테이션이 추가적으로 필요한 지역을 알아보았다.
  - 이를 하나의 테이블화 시켜 확인해보고자 한다.

  ![image](https://user-images.githubusercontent.com/67505208/99069339-8560ed00-25f1-11eb-8721-aebd646c6818.png)

- QGIS에 해당 동의 위치를 확인하여 추가 스테이션을 마킹하고자 한다.
- 이 과정에서 기존 스테이션의 위치를 감안해야 할 것이다. 고려사항은 다음과 같다.
  - 스테이션간 거리 __300m ~ 400m 이격__
  
  ![image](https://user-images.githubusercontent.com/67505208/99070393-7bd88480-25f3-11eb-8c51-1b281acf8401.png)

  - **출퇴근, 등하교** 등의 조건을 감안하여 주거지와 학교,회사 동선으로 유도
  - __여가,레저__ 등의 목적을 감안하여 __호수 공원 및 도심 공원__ 접근성을 강화
  - __인구 증가__ 에 따른 스테이션 개수 추가
  - 교통수단의 편리성을 강화하기 위해 __버스정류장, 지하철역__ 등의 교통 접근성 강화
  
- 중복되는 지역이 많은 것을 확인할 수 있다.
  - 중복지역을 제외하며 17개 지역으로 간추렸다.
  
  ![image](https://user-images.githubusercontent.com/67505208/99070303-4e8bd680-25f3-11eb-891f-b6b3fc2c8670.png)

- 위의 지역에 대해 QGIS를 활용하여 스테이션 추가하였다.

### 신규 스테이션
- 추가한 스테이션에 대한 선정결과를 다음의 예시를 통해 확인해보고자 한다.

![image](https://user-images.githubusercontent.com/67505208/99070657-015c3480-25f4-11eb-8547-5b2cd133748d.png)

![image](https://user-images.githubusercontent.com/67505208/99070724-1f299980-25f4-11eb-9605-2929d9a9eafd.png)

![image](https://user-images.githubusercontent.com/67505208/99070764-349ec380-25f4-11eb-8c7e-02ece086d4ef.png)

![image](https://user-images.githubusercontent.com/67505208/99070799-484a2a00-25f4-11eb-903a-c7f8e254d704.png)

- 추가한 신규 스테이션의 좌표를 확인하고자 한다.

![image](https://user-images.githubusercontent.com/67505208/99071103-d9210580-25f4-11eb-8805-4a7cfa0d0b6a.png)

- 제출형식에 맞게 신규 스테이션의 정보를 가공한다.
  - 우리는 분석과정에서 거치대수에 대해 감안하지 못하였다.
  - 그렇기 때문에 기존 스테이션의 평균 거치대수(25대) 값을 일괄적으로 부여하여 병합하도록 한다.
  
  ![image](https://user-images.githubusercontent.com/67505208/99071316-3e74f680-25f5-11eb-915f-117d0d724767.png)
  ![image](https://user-images.githubusercontent.com/67505208/99071353-52b8f380-25f5-11eb-8a31-0be76fda9a40.png)

- 신규 스테이션 테이블과 기존 스테이션 테이블을 병합하여 통일시키고, 최종 산출값을 출력한다.
![image](https://user-images.githubusercontent.com/67505208/99071444-7b40ed80-25f5-11eb-9514-9d2212e37dee.png)

- __기존 스테이션 164 + 신규 스테이션 35 = 변경 후 스테이션 199의 결과를 출력하였다.__
![image](https://user-images.githubusercontent.com/67505208/99071529-a6c3d800-25f5-11eb-9eab-9a828f9151ed.png)

- 위와 같은 결과를 통해 우리는 다음과 같은 **기대 효과와 한계점**을 도출하였다.
![image](https://user-images.githubusercontent.com/67505208/99071603-ca871e00-25f5-11eb-9b35-8f61a6d6f4a6.png)
