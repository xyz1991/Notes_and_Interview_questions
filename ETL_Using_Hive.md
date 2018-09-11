# Prmary Table creation:  
## Creation of a Table in Hive:  
```SQL
CREATE TABLE pageviews (userid STRING COMMENT 'A sample comment on a column', 
link STRING, 
came_from STRING) 
COMMENT 'This is the a sample table for ETL'
PARTITIONED BY (datestamp STRING) 
CLUSTERED BY (userid) INTO 10 BUCKETS
ROW FORMAT DELIMITED
FIELDS TERMINATED BY ','
LINES TERMINATED BY '\n'
STORED AS TEXTFILE;
```  
  
## Insertion of values using static partition:  
```SQL
INSERT INTO TABLE pageviews PARTITION (datestamp = '2014-09-23')
  VALUES ('jsmith', 'mail.com', 'sports.com'), ('jdoe', 'mail.com', null);
  ```  
    
## Insertion of values using Dynamic partition:  
```SQL
set hive.exec.dynamic.partition=true
  
  
set hive.exec.dynamic.partition.mode=nonstrict;


INSERT INTO TABLE pageviews PARTITION (datestamp)
  VALUES ('tjohnson', 'sports.com', 'finance.com', '2014-09-23'), ('tlee', 'finance.com', null, '2014-09-21');
  ```  
  
## Testing:  
```SQL
select * from pageviews where came_from is NULL; 
```   
  
# External Staging table creation:  
  
## Input Preparations:  
```SQL
cat /tmp/part1
xxx,xx.com,,2018-09-10
yyy,yyy.com,sports.com,2018-09-10
jdoe,mail.com,,2018-09-10
tjohnson,sports.com,finance.com,2018-09-10

cat /tmp/part2
xxx,xx.com,,2018-09-10
yyy,yyy.com,sports.com,2018-09-10
jdoe,mail.com,,2018-09-10
tjohnson,sports.com,finance.com,2018-09-10

hadoop fs -mkdir /user/cloudera/hivetabledir

hadoop fs -copyFromLocal /tmp/part* /user/cloudera/hivetabledir

hadoop fs -ls /user/cloudera/hivetabledir

hadoop fs -cat /user/cloudera/hivetabledir/part*
xxx,xx.com,,2018-09-10
yyy,yyy.com,sports.com,2018-09-10
jdoe,mail.com,,2018-09-10
tjohnson,sports.com,finance.com,2018-09-10
xxx,xx.com,,2018-09-10
yyy,yyy.com,sports.com,2018-09-10
jdoe,mail.com,,2018-09-10
tjohnson,sports.com,finance.com,2018-09-10
```
  
## External Table Creation from data at HDFS location:  
```SQL
CREATE EXTERNAL TABLE pageviewstaging(userid STRING, 
link STRING, 
came_from STRING,
datestamp STRING)
COMMENT 'This is the staging table'
ROW FORMAT DELIMITED 
FIELDS TERMINATED BY ','
LINES TERMINATED BY '\n'
STORED AS TEXTFILE
LOCATION '/user/cloudera/hivetabledir';
```
  
## Testing:  
```SQL
select * from pageviewstaging;
```
  
