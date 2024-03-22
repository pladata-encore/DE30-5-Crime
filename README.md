
![20240113_W6nJMj (1)](https://github.com/pladata-encore/DE30-5-Crime/assets/163955122/e758dd20-5ea3-4b86-b4be-07d3b591e4df)


### 팀원 : 이석희, 김시환, 서유진, 이선경, 김희수


미니 프로젝트 일정 : 2024.03.14 ,2024.03.15, 2024.03.18(3일)

선정 이유 : 매년 증가 추세를 보이는 범죄율에 대해 추후에도 지속적으로 증가할 것으로 예상, 도시별 항목별 분석으로 범죄간의 상관관계를 분석

데이터 수집 : 공공데이터포털(경찰청_범죄 발생 지역별 통계_20151231.csv 활용)

서비스 내용 : 각 지역의 범죄율을 시각화를 통한 심각성을 인지 및 예방 의식 고양

프로젝트 목표 : 수업시간에 배운 python, Linux, mysql, hive, hadoop 프로그램 역할을 이해하고 성능 등을 활용하여 프로그램 간 데이터 이동 연관성 이해

기술스택 :
<img src="https://img.shields.io/badge/linux-FCC624?style=for-the-badge&logo=linux&logoColor=black">
<img src="https://img.shields.io/badge/mysql-4479A1?style=for-the-badge&logo=mysql&logoColor=white">
<img src="https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white">
<img src="https://img.shields.io/badge/apachehive-FDEE21?style=for-the-badge&logo=apachehive&logoColor=black">
<img src="https://img.shields.io/badge/apachehadoop-66CCFF?style=for-the-badge&logo=apachehadoop&logoColor=white">
<img src="https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">

**목표** 

- 수업 때 배운 내용들을 활용해서 파일을 분석해 시각화 하기

**목차**

1. 데이터 사용을 위해 jupyter lab을 이용한 간단한 전처리
2. 데이터를 하둡에 적재 후 하이브에서 불러오기
3. 하이브 데이터를 mysql로 export
4. mysql bench를 리눅스와 연동 후 테이블 체크
5. 파이썬에서 데이터를 불러와서 분석 및 시각화

**데이터 사용을 위해 jupyter lab을 이용한 간단한 전처리**

공공데이터포탈에서 받아온 csv 자료를 python의 pandas를 사용해 데이터 프레임 형태로 만들기
![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163943356/c33ce21e-14d2-4438-aed1-ce1c00cdd7d5)

**데이터를 하둡에 적재 후 하이브에서 불러오기**

하둡에 넣어 PATH를 이용해 외부테이블로 데이터를 불러온다
![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163943356/f8ad7733-923e-4adf-a0bd-0d6e6bed98db)
group by 를 이용해 확인해보면
![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163943356/95251751-47c9-486b-b732-2da018ccc3c5)

**하이브 데이터를 mysql로 export**

![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163943356/e7bc013d-e700-4bd2-b10b-8948785ea31d)

**mysql bench를 리눅스와 연동 후 테이블 체크**

![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163943356/e32a9872-b1f4-4184-9048-304b57f21baa)

**파이썬에서 데이터를 불러와서 분석 및 시각화**

![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163943356/319f42a8-dd6f-4be7-85e8-91a7d973516e)
데이터들을 파이썬에서 시각화하였다.

