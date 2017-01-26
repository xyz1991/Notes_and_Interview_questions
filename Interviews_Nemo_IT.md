# 1st Interview
Brief the resume?<br />
What are the kind of tables used in Hive?Why?<br />
External table- When you want for Data retrival after droping the table<br />
Internal table- to add data to the already exsiting table.<br />
Turning Hive queries?(Small table, Big table, Distributed cache)<br />
Partionting and Bucketing difference?<br />
Hive Queries:-<br />
select * from Data => No Mapper & No Reducer<br />
where = "" => Mappers only<br />
Group by = "" => Reducer only<br />
UDF's in Hive and Hwo do you Implement it?<br />
Difference between Impala and Hive?<br />
Yarn Resources?<br />
Disadvantages of Impala?(speculative execution)<br />
Sqoop => Oracel to HDFS<br />
Tablue data vizulalization?<br />
Spark => Difference between action and transformation?<br />
How WebLog and Transaction information to be processed by Big Data is Generated(Data Sources People(Social Media), Machines(WebLogs), Organisation(Transactions))?  
What is an RDD in spark?(Chapter 3 Spark Data Analytics cook book)  

# 2nd Interview
Map/reduce if 1st file had empId and empName & 2nd file empId and empSalary. How to find the max salary empId? How many mappers are launched?<br />
Invalidate metaData command in Impala?<br />
How to load UDF's in Hive?<br />
How to change default memory parameters in Hive using set command?<br />
Case class in SparkSQL?<br />
What is spark executor?<br />
What is splittablity and block compression and How does it effects different file formats like CSV, JSON, XML, AVRO and Parquet?  
Falut Tolerence and high availability in HDFS?(Replication and Speculative execution)  
Difference between object, method, functions and classes?(Objects are instances of classes, whose class Functions can be acssed as methods)  
Difference between public, private and default value decrelation?  
is val and var public, private and default decrelation?  
deceralation of public, private and default types in python?  
Difference between a Data Engineer, Data Analyst and Data Scientist?  
Difference between where and havings clauses in SQL?  
Changing file permissions in Shell Scripting?  
Difference between Map side and reduce side joins?  
Difference between GroupBy, OrderBy, sortBy, DISTRIBUTE BY and CLUSTER BY x?  
GroupBy=> Aggregates the Data into groups like using SUM, Avg etc.. on a cloumn.  
ORDER BY guarantees global ordering, but does this by pushing all data through just one reducer. This is basically unacceptable for large datasets. You end up one sorted file as output.  
SORT BY x: orders data at each of N reducers, but each reducer can receive overlapping ranges of data. You end up with N or more sorted files with overlapping ranges.  
DISTRIBUTE BY x: ensures each of N reducers gets non-overlapping ranges of x, but doesn't sort the output of each reducer. You end up with N or unsorted files with non-overlapping ranges.  
CLUSTER BY x: ensures each of N reducers gets non-overlapping ranges, then sorts by those ranges at the reducers. This gives you global ordering, and is the same as doing (DISTRIBUTE BY x and SORT BY x). You end up with N or more sorted files with non-overlapping ranges.  
So CLUSTER BY is basically the more scalable version of ORDER BY.  
