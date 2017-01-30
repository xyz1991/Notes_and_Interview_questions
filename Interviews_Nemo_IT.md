# 1st Interview
Brief the resume?<br />
What are the kind of tables used in Hive?Why?<br />
External table- When you want for Data retrival after droping the table<br />
Internal table- to add data to the already exsiting table.<br />
Turning Hive queries?(Small table, Big table, Distributed cache)<br />
What is Partioning and bucketing in hive & Partionting and Bucketing difference?<br />
Hive Queries:-<br />
DIfference between where and having clauses?  
HAVING is used to check conditions after the aggregation takes place.  
WHERE is used before the aggregation takes place.  
The HAVING clause was added to SQL because the WHERE keyword could not be used with aggregate functions.  
select * from Data => No Mapper & No Reducer<br />
where = "" => Mappers only<br />
Group by = "" => Reducer only<br />
UDF's in Hive and Hwo do you Implement it?<br />
Difference between Impala and Hive?<br />
  
  
Difference between Map-reduce and spark? Advantages and disadvantages and execution methods.  
Conceptually DAG model is a strict generalization of MapReduce model. DAG-based systems like Spark and Tez that are aware of the whole DAG of operations can do better global optimizations than systems like Hadoop MapReduce which are unaware of the DAG to be executed.  
  
Long version:   
Conceptually speaking, the MapReduce model simply states that distributed computation on a large dataset can be boiled down to two kinds of  computation steps - a map step and a reduce step. One pair of map and reduce does one level of aggregation over the data. Complex computations typically require multiple such steps. When you have multiple such steps, it essentially forms a DAG of operations. So a DAG execution model is essentially a generalization of the MapReduce model.  
  
While this is the theory, different systems implement this theory in different ways, and that is where the "advantages" and "disadvantages" come from. Computations expressed in Hadoop MapReduce boil down to multiple iterations of (i) read data from HDFS, (ii) apply map and reduce, (iii) write back to HDFS. Each map-reduce round is completely independent of each other, and Hadoop does not have any global knowledge of what MR steps are going to come after each MR. For many iterative algorithms this is inefficient as the data between each map-reduce pair gets written and read from filesystem. Newer systems like Spark and Tez improves performance over Hadoop by considering the whole DAG of map-reduce steps and optimizing it globally (e.g., pipelining consecutive map steps into one, not write intermediate data to HDFS). This prevents writing data back and forth after every reduce.   
  
Storm, being a streaming system, is slightly different from the batch processing systems referred earlier. It also sets up a DAG of nodes lets the records stream between the nodes. Its best to compare Storm with Spark Streaming (streaming system built over Spark) than Hadoop MapReduce. Both accepts a DAG of operations representing the streaming computation, but then process the DAG in slightly different ways. Storm sets up a DAG of node and allocates each operation in the DAG of ops to different nodes. Spark Streaming does not pre-allocate, rather uses the underlying Spark's mechanisms to dynamically allocate tasks to available resources. This gives different kinds of performance characteristics.  
  
Yarn Resources and peformane tuning?<br />
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
GroupBy=> Aggregates the Data into groups like using SUM, Avg etc.. on a cloumn. The GROUP BY clause’s purpose is summarize unique combinations of columns values. Often group by is followed by order by or cluster by cluases.  
ORDER BY guarantees global ordering, but does this by pushing all data through just one reducer. This is basically unacceptable for large datasets. You end up one sorted file as output.  
SORT BY x: orders data at each of N reducers, but each reducer can receive overlapping ranges of data. You end up with N or more sorted files with overlapping ranges.  
DISTRIBUTE BY x: ensures each of N reducers gets non-overlapping ranges of x, but doesn't sort the output of each reducer. You end up with N or unsorted files with non-overlapping ranges.  
CLUSTER BY x: ensures each of N reducers gets non-overlapping ranges, then sorts by those ranges at the reducers. This gives you global ordering, and is the same as doing (DISTRIBUTE BY x and SORT BY x). You end up with N or more sorted files with non-overlapping ranges.  
So CLUSTER BY is basically the more scalable version of ORDER BY.  

#3rd Interview  
Sabre architecture?  
UDFs in Spark and Hive?  
Changing File permission in Hive?  
What is DML and DDL?  
DML is abbreviation of Data Manipulation Language. It is used to retrieve, store, modify, delete, insert and update data in database.  
Examples: SELECT, UPDATE, INSERT statements  

DDL is abbreviation of Data Definition Language. It is used to create and modify the structure of database objects in database.  
Examples: CREATE, ALTER, DROP statements  
What are dirvers and executers in Spark?  
Explain the Process of Spark Streaming?  
Why is Spark conf and spark context related to the program?  
How to enable speculative execution in spark?  
spark-submit \  
--conf "spark.speculation=true" \  
--conf "spark.speculation.multiplier=5" \  
--conf "spark.speculation.quantile=0.90" \  
--class "org.asyncified.myClass" "path/to/uberjar.jar"    
  
    
Primary key vs unique key in SQL?  
Primary Key:  
Can be only one in a table  
In some DBMS it cannot be NULL - e.g. MySQL adds NOT NULL  
Primary Key is a unique key identifier of the record  
Unique Key:  
Can be more than one unique key in one table  
Unique key can have null values  
It can be a candidate key  
Unique key can be null and may not be unique  
