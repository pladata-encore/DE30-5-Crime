MySQL 계정 : root

database 이름 : crime

table 이름 : cities

경로 : user/root/crime/


![1](https://github.com/pladata-encore/DE30-5-Crime/assets/158540157/af06ce49-2bc3-4335-a290-84470891e939)

: MySQL 접속

mysql -u [경로] -p

![2](https://github.com/pladata-encore/DE30-5-Crime/assets/158540157/914ed195-bb56-40d3-a724-75a667b9cb0b)

: mysql database 생성

create database [database명];

![3](https://github.com/pladata-encore/DE30-5-Crime/assets/158540157/5a9b17ff-88ac-40e5-8ed0-9fb923bad4ba)

: crime database에 들어가서

![4-2](https://github.com/pladata-encore/DE30-5-Crime/assets/158540157/25c24967-67ba-4218-a2fa-4f15f3f16adf)

: 컬럼명을 작성 후 각 값의 varch(50)으로 cities table 생성

![4](https://github.com/pladata-encore/DE30-5-Crime/assets/158540157/16e36851-7a46-47aa-b462-02d5a0b3ab56)

: table 생성 확인

DISCRIBE [table명];

![5](https://github.com/pladata-encore/DE30-5-Crime/assets/158540157/0a66f6cb-05b3-44e2-9246-f72bfdda2176)

: 

= 기존버전
sqoop export \
--connect jdbc:mysql://mysql_host:port/database \
--username your_usermame \
--password password \
--table target_table \
--export-dir /user/hive/source \


= 활용버전
sqoop export \
--connect jdbc:mysql://localhost:3306/crime \
--username root \
--password T@chmaki87 \
--table cities \
--export-dir /user/root/crime \

![6](https://github.com/pladata-encore/DE30-5-Crime/assets/158540157/81be3d01-0a99-404b-88fc-e7da33714149)
