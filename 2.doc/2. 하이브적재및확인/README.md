![하이브적재](https://github.com/pladata-encore/DE30-5-Crime/assets/163947687/b8d9bb07-7779-49b1-8d1e-f5219c4e11cd)
[root@localhost ~] hadoop fs -put police2.csv /user/root/crime  
[root@localhost ~] hadoop fs -chmod 777 /user/root/crime/police2.csv  
[root@localhost apache-hive]# hive  
hive> create database crime;  
hive> use crime;  
hive> create table cities  
(seoul string, busan string, daegu string, incheon string, gwangju string, daejeon string, ulsan string, sejong string, gyeonggido string, gangwondo string, chungcheongdo string, Jeollado string, gyeongsangdo string, jejudo string, othercities string, nonurbanareas string)  
row format delimited  
fields terminated by ','  
lines terminated by '\n'  
stored as textfile  
location '/user/root/crime'  
;  
hive> load data inpath '/user/root/crime' into table cities;  
hive> show tables;  
hive> select * from cities;  
