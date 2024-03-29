# 주유소 데이터 수집 및 분석
<br>

## 프로젝트 개요
-----

![image](https://github.com/gaeju/opinet/assets/100760127/ab71ad0b-d9e4-4aa1-b7c1-a040c1039d70)

셀프 주유소가 더 쌀까? 

유가 데이터를 수집하고 분석하며 정말 셀프 주유소가 저렴한지에 대해 비교 분석해보는 프로젝트를 진행하였습니다.
<br>

## 데이터 수집
- 오피넷(https://www.opinet.co.kr/user/main/mainView.do)에서 셀레니움을 이용해 데이터 수집을 진행하였음
- 추가로 구글맵 api를 이용해 위도, 경도 정보를 수집
![image](https://github.com/gaeju/opinet/assets/100760127/aaf41bd2-33ff-44ee-a662-37be9d77ee91)

<br><br>

## 데이터 분석
- 셀프 주유소 전체 평균 비교
![image](https://github.com/gaeju/opinet/assets/100760127/98ae2354-fc24-4a20-ab8c-808cfc49c257)
- 셀프 주유소 구별 평균 비교
![image](https://github.com/gaeju/opinet/assets/100760127/1a2c96b1-e6d0-4186-ada4-e1966b63e7ee)

- 구별 셀프 주유소 경유 가격 비교
  ![image](https://github.com/gaeju/opinet/assets/100760127/8c96126d-8a20-4876-bcd1-d00ca0536c05)
- 구별 셀프 주유소 휘발유 가격 비교
  ![image](https://github.com/gaeju/opinet/assets/100760127/483025d3-dafe-4188-9db2-28d4b36bafbd)
- boxplot을 이용하여 브랜드 별 셀프 주유소 여부 가격 비교
  ![image](https://github.com/gaeju/opinet/assets/100760127/dee61658-38a9-4cdb-95fe-32c79ec0cfd1)

<br><br>

## 결과 및 결론
### 결과
1. pivob_table을 이용하여 구별 데이터 집계 결과
- 전체 평균적으로 봤을 때 경유는 대략 168원, 휘발유는 대략 176원 정도의 셀프 주유소가 더 저렴
- 구별로 셀프 주유소 여부에 따른 경유, 휘발유 가격 비교 결과 셀프 주유소가 더 높은 것 같았으나 비교하기가 힘들어 시각화 진행
  
경유: 
- 대체로 셀프주유소가 더 저렴
- 서대문구나 은평구는 셀프주유소가 아닌 곳이 더 저렴 
- 강북, 광진, 성북구의 경우는 차이가 거의 나지 않았다
- 중구나 강남구가 셀프 주유소 여부에 대해 차이가 많이 났다

휘발유: 
- 한 곳도 빠짐없이 셀프 주유소가 더 저렴
- 서대문구나 성북구의 경우 차이가 거의 나지 않은 것을 확인하였다.
- 휘발유도 경유와 마찬가지로 강남구나 중구에서 차이가 큰 것을 확인하였다.

\* 단 용산구의 경우 전체 주유소 중에 셀프 주유소인 곳이 존재하지 않아 비교를 할 수 없었음
<br>

2. pivob_table을 이용해서 브랜드 별로 비교하기
- 한 곳도 빠짐 없이 셀프 주유소가 일반 주유소보다 저렴했음
- pb 브랜드는 셀프 주유소가 없어서 비교할 수가 없었음
- 대략적으로 확인은 하였으나 비교하기가 힘들어 시각화 진행
<br>

3. boxplot을 이용하여 브랜드 별 셀프 주유소 여부 가격 비교
![image.png](attachment:image.png)
- 가격의 편차는 sk에너지와 gs칼텍스가 가장 컸음
- 가격의 평균도 sk에너지와 gs칼텍스가 가장 큼
- pb를 제외한 다른 브랜드 모두 이상치가 있었으나 hd 현대 오일 뱅크나 s-oil의 이상치가 두드러져 추가적인 분석을 하면 좋을 듯 함
- 알뜰 주유소의 가격이 가장 알뜰함
- 비교해봤을 때 확실히 self 주유소의 가격이 일반 주유소의 가격보다 저렴한 것을 다시 한번 확인하였음

### 결론
 셀프주유소와 일반 주유소의 비교를 위해 두가지 기준으로 비교를 진행하였습니다.첫번째로 구별 비교, 두번째로 브랜드별 비교. 
 비교를 위해 각자 pivot_table을 이용하여 수치를 도출하였으며 시각화를 이용하였습니다.
 첫번째인 구별 비교의 결과 경유의 경우에는 대체로 셀프주유소가 저렴하였지만 서대문구나 은평구의 경우를 제외하고는 셀프주유소가 더 저렴하였습니다
 서대문구나 은평구의 경우도 그 차이가 미미하였으며 다른 구와 비교해 보았을 때 셀프 주유소의 가격이 비싼것이 아닌 일반 주유소의 가격이 저렴한 편인 것을 확인하였습니다. 휘발유는 구별 구분 없이 셀프 주유소의 가격이 더 저렴하였습니다. 단, 용산구의 경우에는 셀프 주유소가 없어 비교할 수 없었습니다.
 두번째인 브랜드별 비교에서는 전부 셀프 주유소가 저렴한 것을 확인하였습니다. 단, 브랜드 pb는 셀프 주유소가 없어 비교가 불가능하였습니다.
 또한 전체 평균을 비교한 결과에서도 셀프 주유소와 일반 주유소는 경유 168원, 휘발유 176원이 차이가 났습니다. 결론적으로 셀프주유소가 일반 주유소에 비해 저렴하며 그 이유에 대해서 다양한 뉴스와 기사들을 살펴본 결과 셀프 주유소가 인건비가 덜 들어가서 기름의 가격을 결정하는데 영향을 끼쳤을 것이라는 결론을 내렸습니다.

## 부록
### 관련 기사
- 'https://m.yonhapnewstv.co.kr/news/MYH20231103017700641'
- 'https://www.mstoday.co.kr/news/articleView.html?idxno=86087'
### 데이터 출처
오피넷: https://www.opinet.co.kr/searRgSelect.do
