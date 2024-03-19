<파이썬 참고>\
!pip install dbfread #처음 다운받은 지도 그래프의 파일 형식을 불러오기위해 설정함\
!sudo apt-get install -y fonts-nanum #한글을 사용하기 위한 폰트 설\
!sudo fc-cache -fv #새로 설치된 폰트를 적용하기 위해 캐시를 갱신\
!rm ~/.cache/matplotlib -rf # 이전에 캐시한 폰트 설정 등의 정보를 제거\
필요한 패키지를 다운\

<지도 데이터는 ctp_rvn.shp를 사용>\
%env SHAPE_RESTORE_SHX=YES\
!ogrinfo -repair geometry ctp_rvn.shp \
#dbf를 불러오려다 결국 실패 다른 파일형식인 shp를 사용하기 위한 깨짐방지 설정 \
*지도 데이터를 찾기위해 국토지리정보원이나 주소기반산업지원서비스 등 다양한 지도 데이터를 제공해주는 사이트를 찾아 아이디를 만들고 다운을 받으려했지만 신청기간이 있어 포기하고 지오서비스웹에서 어떤 분이 만든 데이터를 추출함(내가 받아보고 열어보는 시도를 했던 파일들)\
![스크린샷 2024-03-19 115448](https://github.com/pladata-encore/DE30-5-Crime/assets/163955122/d1ba7fe3-5ff8-4a38-9530-405400369718)

\
잘 가져온건지 파일 시각화 해보기\
![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163955122/1ecb127d-b0b9-4987-b2f0-1ce773df51a1)

\
우리 데이터를 대입하기 위해 지도 그래프 안의 내용을 불러들어옴\
#그러나 한글이 깨져서 코드에 'cp949'를 넣어서 시도해봄\
#한글은 잘나왔으나 서울,제주도처럼 간단하게 쓴 우리와 다르게 그 안에는 서울특별시,제주특별자치도로 사용됨(수정)\
![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163955122/57f045e2-c2aa-444a-81f8-f5ee336800b1)

\
우리조는 배웠던 데이터 가져오기를 수십번 시도를 해봤지만 실패하여 결국 데이터 프레임을 사용하여 데이터를 설정함\
![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163955122/b17c681d-9412-4a84-b62f-6cfdda95ce41)

\
가져올 패키지를 설정하고 지도 그래프 파일과 데이터 프레임을 합쳐 첫 시도로 강력범죄 발생 건수를 시각화 해봄\
#나오지 않고 한글도 꺠지고 무슨 문제일까 지도 데이터 경로도 바꿔보고 열로 설정되있는 '도시'도 지도 데이터의 내용인 CTP_KOR_NM로 바꿔 설정하고 한글폰트도 정함\
![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163955122/b34f456f-1371-4891-8e54-efc3a6f332d7)

\
결과적으로 잘 나옴 수치를 그라데이션으로 표현되고 어느 지역이 가장 많이 발생한지 명확하게 보이는 우리의 의도와 같은 생각으로 나온게 좋았음\
#그러나 우리가 예상한 서울 경기 지역인 즉 수도권지역이 사람이 많아 많은 범죄 발생으로 인해 너무 극과 극인 색깔만 보임\
![스크린샷 2024-03-18 175107](https://github.com/pladata-encore/DE30-5-Crime/assets/163955122/781975f6-156b-44f8-9e83-2434f9d77994)

\
좀 더 자세한 표현을 위해 서울과 경기지역의 수를 지우고 깔끔함을 위해 축도 지우고 재정비해서 다시 실행시킴(좀 더 다양한 컬러감이 나옴)\
![스크린샷 2024-03-19 143932](https://github.com/pladata-encore/DE30-5-Crime/assets/163955122/c94dd98b-274b-4656-92ea-e23a28b4d72e)

\
우리는 수도권을 포함하여 아예 다른 여러 색깔들을 놓으면 명확하게 보이지 않을까 하며 다시 데이터 프레임을 만들고 색깔을 수정해봄(범죄도 다르게해서)\
![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163955122/188e6302-fc5b-4f5f-8205-868009db23ee)

\
보기엔 명확했으나 점도를 사용한 심각성 인지나 표현력부분에서 아쉽다고 생각하여 그라데이션으로 하되 색깔을 바꿔봄(색깔은 지피티가 도와줌)\
![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163955122/75280470-72fd-4ad7-8595-491deaf6f687)

\
또 다른 시각화를 위해 우리는 어느 지역이 가장 심각한지 당연한 1,2등인 경기와 서울을 제외한 값을 더하여 총 범죄 발생량을 지도 그래프로 표현\
![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163955122/66f6faf9-64ff-4c89-bf05-c477de0a8154)

보면 전국 3등 인구수인 부산이 다음으로 가장 많이 발생하는 것을 알 수 있다. 그다음 경상남도,인천 순

\
이제 어떤 범죄가 가장 많이 발생하는지 시각화 해보았고 다양한 그래프를 시도해 봄\
![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163955122/c6a824c9-1268-4956-9f4b-04775e3351b1)
너무 기본적임\
![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163955122/f8e34bdc-44d5-46d1-941a-981e4d7a3151)
너무 안보이고 어떤 수치인지도 명확하지 않음\
![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163955122/4a148ebb-27f4-4cba-8b50-5fb213a03163)

지도그래프와 같이 명확하고 차가움과 위험함을 표현하는 색감까지 좋아서 채택!\
결과적으로 교통>지능>폭력 순으로 많은 걸 알 수 있다

\
이젠 각 지역별로 어떤 범죄가 많이 일어나는지 원 그래프와 퍼센트를 사용하여 지표의 크고 작음이 더 잘 나타낼 수 있도록 하기 위해\
데이터 프레임을 다시 불러 퍼센트 코드를 짜고 그래프를 불렀지만 칼럼에 대한 글자 에러가 나서 칼럼이 문제인것같아 칼럼과 인덱스를 바꿈\
그러나 여전히 에러 다시 돌아와서 에러를 지피티한테 물어서 수정하여 시도한 결과 고르게 표현됨\
![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163955122/27bbf80c-a34d-431e-bdf1-599cd1a263e7)
![image](https://github.com/pladata-encore/DE30-5-Crime/assets/163955122/0ae0aff5-9f35-43dd-b273-e829f718c76e)

가장 많은 양의 경기도와 서울만 구현\

총 범죄량과 다르게 서울은 안보범죄를 경기도는 환경범죄가 많다는 것을 알 수 있다.
