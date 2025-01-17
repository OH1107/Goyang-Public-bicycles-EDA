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
- 코로나에 의해 영향을 받은 오프라인, 온라인별 업종은?
  - 코로나에 의한 영향인지 혹은 계절성 변동인지 파악
  - 업종별 소비 건수의 증감을 확인하고 이에 대한 인과관계를 파악하고자 함
- 코로나에 영향 받은 업종들 중 성별, 연령대별 집단의 유의미한 변화 탐색
  - 업종내 유의미한 변동이 있었던 집단을 추출하고 인과관계를 파악하고자 함
- 코로나가 소비트렌드에 어떤 변화를 불러 일으켰는지 키워드를 통해 제시
## 데이터
- 분석환경 내 제공 데이터
  - MBN : *매일경제 뉴스데이터*
  - __엠코퍼레이션 : *금융사 데이터를 기반으로 한 온라인 상품 구매 데이터*__
  - __삼성카드 : *오프라인 상품 구매 데이터*__
  - __신한카드 : *오프라인 상품 구매 데이터*__
  - 지인플러스 : *전국 아파트 시세 및 거래량 데이터*
  - KDX : *무료데이터*
    - __코로나 확진자 데이터__
- 기타 활용 가능 데이터
  - 공공데이터 : *공공 데이터명 및 링크 표시*
  - 법적 문제없는 크롤링 데이터 : *크롤링 코드 필수*
  
- Bold체 데이터 셋 = 본 프로젝트를 위해 사용했던 데이터
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

- 코로나가 발생한 시점을 기준으로 비교하기 위해 2019년 상반기, 2020년 상반기 데이터를 추출
  - 카드 사용 데이터는 **2019년 1월 부터 2020년 6월**까지의 데이터로 구성되어 있음

![image](https://user-images.githubusercontent.com/67505208/100613548-13f69d80-3358-11eb-93b8-240d1ef1d7c0.png)

- Mcorporation에서 제공한 카드 데이터 셋으로 **온라인 상품 구매 이력**을 분석하고자 한다.

![image](https://user-images.githubusercontent.com/67505208/100613806-764f9e00-3358-11eb-8868-d272d43d0ba0.png)

- 카테고리별 나누어져 있는 데이터를 하나의 데이터 프레임으로 병합

![image](https://user-images.githubusercontent.com/67505208/100613993-c3337480-3358-11eb-8f68-c9598909439a.png)

  - 다음과 같이 하나의 데이터프레임으로 병합하였다.
  
  ![image](https://user-images.githubusercontent.com/67505208/100614352-5c628b00-3359-11eb-804d-80d0cffbc3fe.png)

![image](https://user-images.githubusercontent.com/67505208/100846461-e594d180-34c1-11eb-9972-43e813006689.png)

![image](https://user-images.githubusercontent.com/67505208/100846535-fcd3bf00-34c1-11eb-92cb-5d200035c44b.png)

- 코로나 확진자의 증가에 따른 소비건수의 변화를 알아보기 위해 다음의 데이터를 사용

![image](https://user-images.githubusercontent.com/67505208/100846832-5805b180-34c2-11eb-8266-376db31f50a2.png)

- [코로나바이러스감염증-19 현황 누적 데이터](https://kdx.kr/data/view?product_id=25918)

![image](https://user-images.githubusercontent.com/67505208/100847331-0873b580-34c3-11eb-9139-53f97dfc3bdc.png)

![image](https://user-images.githubusercontent.com/67505208/100847425-29d4a180-34c3-11eb-8094-2a84b4c580d4.png)

![image](https://user-images.githubusercontent.com/67505208/100847807-9b145480-34c3-11eb-94a7-d3bcb2a83c28.png)

- 그래프를 통해 확진자가 **2월 말, 3월 초**를 기점으로 크게 늘어나는 것을 확인할 수 있다.
- 8월경에도 확진자가 증가하는 추세를 확인할 수 있으나, **카드사용 데이터는 6월 말까지만 존재하므로 2, 3월의 확진자 증가 추이만을 사용하도록 하겠다.**

![image](https://user-images.githubusercontent.com/67505208/101027142-17d62a00-35bb-11eb-8b77-616772324ddc.png)

- 파란 막대 그래프는 카드사용건수를 나타내며, 빨간 꺽은선 그래프는 코로나 일일확진자 수를 나타낸다.
  - 중간의 빨간 세로선을 기점으로 왼쪽은 2019년 2월, 3월 / 오른쪽은 2020년 2월과 3월이다.

![image](https://user-images.githubusercontent.com/67505208/101455821-7cf09d80-3976-11eb-9520-7102bd10961e.png)

- 삼성카드 데이터와 신한카드 데이터를 합친 **오프라인 카드 사용데이터의 총 사용건수의 변화**를 확인해본다.
  - 전년대비 코로나가 유행했던 2월, 3월의 소비건수는 약 7% (7.7억 건)의 감소한 것을 확인할 수 있다.
  
![image](https://user-images.githubusercontent.com/67505208/101456149-f5eff500-3976-11eb-8456-c01a60697b40.png)

- 업종별로 원하는 기간동안의 소비건수를 보다 편하게 추출하기 위한 함수를 정의한다.
- 또한 업종별 소비건수와 코로나 확진자수의 상관관계를 대조하기 위한 함수를 정의한다.
  - 정의한 함수를 통해 다음의 히트맵을 출력했다.
  
![image](https://user-images.githubusercontent.com/67505208/101456432-5f700380-3977-11eb-8dcc-341def52caef.png)

![image](https://user-images.githubusercontent.com/67505208/101456469-7151a680-3977-11eb-93d0-e4ec6a227650.png)

- 히트맵을 통해서 다음의 결과를 확인할 수 있었다.
  - 오프라인 카드이력에 존재하는 업종들은 모두 코로나 일일확진자 수와 음의 상관관계를 가지고 있다.
    - 즉 코로나가 확산될수록, 해당 업종의 소비는 감소하였다.
  - 업종별로 코로나 일일확진자 수와 상관관계(이하 코로나와의 상관관계)가 각기 다르다.
    - 예: **'여행/교통'의 경우 코로나와 -0.56의 상관계수**를 갖고있지만, **할인점/슈퍼마켓은 약한 음의 상관관계 -0.11을 기록하고 있다.
  - 또한 업종간 서로 높은 상관관계를 갖고 있는 업종군이 존재한다.
    - 예: '스포츠/문화/레저'와 '여행/교통'은 서로 높은 양의 관계를 갖고 있으며, 서로 상호연관성이 있는 업종으로 판단된다.
    
- 히트맵을 통해 확인된 결과를 활용하여
  - 코로나와 상관관계가 유의한 업종을 선별하였다.
  - 선별한 업종들 간에 상관관계가 높은 것끼리 군집으로 묶어 분석하고자 한다.
    - 여가 : '스포츠/문화/레저', '여행/교통'
    - 뷰티 : '미용', '백화점/상품권/아울렛', '패션/잡화'
    - 외식 : '요식/유흥'
    - 교육 : '교육/학원'
    
- 코로나와 업종간 상관관계가 **우연의 일치로 존재한 것인지, 혹은 직간접적인 영향을 받아 증감한 것인지** 검증하고자 한다.

- 분석에 앞서 분석을 용이하게 하기 위한 함수를 정의한다.
```python
# 함수: 전년대비 소비변화량 시각화
def barchart(onoff=0, category = 'category'):
    df = categorical_cnt(onoff, category)
    df_2019 = df[df['날짜'].str.contains('2019')]
    df_2020 = df[df['날짜'].str.contains('2020')]

    a = df_2019['소비건수'].sum()
    b = df_2020['소비건수'].sum()
    c = b-a
    d = round(c/a * 100)

    if onoff == 0 :
        e = str(abs(c)) + '건 증가' + '\n' + str(abs(d)) + '% 증가'
        plt.rcParams['figure.figsize'] = [6, 4]
        labels = ['2019년','2020년']
        width = 0.5

        fig, ax = plt.subplots()
        rects1 = ax.bar(0, height=a, width=width, label='2019년', color='yellowgreen', alpha=0.5)
        rects2 = ax.bar(0.5, height=b, width=width, label='2020년', color='yellowgreen', alpha=0.9)

        ax.set_ylabel('구매건수',fontsize=16,fontproperties=fprop)
        ax.set_xlabel('년도',fontsize=16,fontproperties=fprop)
        ax.set_title( category +'구매건수',fontsize=20,fontproperties=fprop)
        ax.annotate(str(a)+'건',xy=(-0.1,a-a*0.05),fontsize=12,fontproperties=fprop)
        ax.annotate(str(b)+'건',xy=(0.4,b-b*0.07),fontsize=12,fontproperties=fprop)
        ax.annotate(e, xy=(0.25,b/2),size=13, ha='center', va="center", bbox=dict(boxstyle="round", alpha=0.8, ec="gray"),fontproperties=fprop)
        ax.set_xticks(x)
        ax.set_xticklabels(labels, fontsize=14)
        for label in ax.get_xticklabels() :
            label.set_fontproperties(fprop)
        ax.legend(loc='lower left',prop=fprop)
        plt.show()
    else:
        e = str(abs(c))[:-2] + '건 감소' + '\n' + str(abs(d)) + '% 감소'
    
        plt.rcParams['figure.figsize'] = [6, 4]
        labels = ['2019년','2020년']
        width = 0.5

        fig, ax = plt.subplots()
        rects1 = ax.bar(0, height=a, width=width, label='2019년', color='skyblue', alpha=0.4)
        rects2 = ax.bar(0.5, height=b, width=width, label='2020년', color='skyblue', alpha=0.8)

        ax.set_ylabel('구매건수',fontsize=16,fontproperties=fprop)
        ax.set_xlabel('년도',fontsize=16,fontproperties=fprop)
        ax.set_title( category +'구매건수',fontsize=20,fontproperties=fprop)
        ax.annotate(str(a)[:-2]+'건',xy=(-0.1,a-a*0.05),fontsize=12,fontproperties=fprop)
        ax.annotate(str(b)[:-2]+'건',xy=(0.4,b-b*0.07),fontsize=12,fontproperties=fprop)
        ax.annotate(e, xy=(0.25,b/2),size=13, ha='center', va="center", bbox=dict(boxstyle="round", alpha=0.8, ec="gray"),fontproperties=fprop)
        ax.set_xticks(x)
        ax.set_xticklabels(labels, fontsize=14)
        for label in ax.get_xticklabels() :
            label.set_fontproperties(fprop)
        ax.legend(loc='lower left',prop=fprop)
        plt.show()
```

![image](https://user-images.githubusercontent.com/67505208/101984556-87d46680-3cc5-11eb-9627-c0b8a391961d.png)

![image](https://user-images.githubusercontent.com/67505208/101984571-a9cde900-3cc5-11eb-82a5-8b1da40f5ab2.png)

![image](https://user-images.githubusercontent.com/67505208/101984583-c5d18a80-3cc5-11eb-8c73-71b65527ebc6.png)
![image](https://user-images.githubusercontent.com/67505208/101984588-cf5af280-3cc5-11eb-9cf0-74b221c4128d.png)

![image](https://user-images.githubusercontent.com/67505208/101984640-06310880-3cc6-11eb-8dfb-605d36dd3b0b.png)

![image](https://user-images.githubusercontent.com/67505208/101984643-0df0ad00-3cc6-11eb-8961-10c1c58157fb.png)

---
- 이와 같은 방법으로 온라인 업종별(엠코퍼레이션 데이터) 분석을 실시하였다.
- 추가적인 정보는 본 리포에 업로드한 소스코드와 분석보고서를 통해 전달하고자 한다.
