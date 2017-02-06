# 1st Interview
  
##Brief the resume?  
I’m a Hadoop Developer with hands on experience in performing Data Analytics using Hadoop components like Spark, SparkSQL, Spark-Streaming, Hive and Impala with in-depth understanding of Hadoop Map-reduce and distributed file systems architecture. I have mainly worked on Parsing, filtering and Manipulating different kinds of Semi-Structured, Unstructured and Structured data.  
  
My most recent project is at Sabre in Southlake TX, which is the largest Global Distribution Systems provider for air bookings in North America. Sabre processes more than 1.5 billion daily API requests. The systems should quickly cull through billions of possibilities to return the most appropriate itineraries to travel shoppers. Data from these data points coming through travel agencies could be structured and unstructured in few cases. All this data was collected, aggregated and analyzed in the Hadoop clusters to find customer usage patterns which helps make cross sell, up sell business decisions and device targeted marketing strategies.  
  
## Few tasks you have done at sabre?  
•	Worked on parsing and filtering Semi-Structure data like json using Dataframe/SparkSQL, case classes and also programmatically specifying the schema explicitly in-addition to working on loading more than 22 features into case classes in Spark.  
•	Worked on modeling data using Avro schema into Parquet format using SparkSQL.  
•	Worked on querying the unstructured text data using Vector Space Models and Apache Lucene.  
•	Worked on real-time data analytics in SparkStreaming for streaming text and kafka topic data.  
•	Worked on loading data to and from RDBMS to HDFS using Spark and JDBC connectors.  
•	Worked on data preparation methods in spark dataframes using set operations, regular expressions, sorting, parsing arbitrary date/time inputs and converting json arrays values into lists.  
•	Worked on installing and pointing the Zeppelin to the Spark master in-addition to creation of custom defined functions.  
•	Exploring of Spark improving the performance and optimization of the existing algorithms in Hadoop using Spark context, Spark-SQL, Data Frame, pair RDD's.  
•	Designed Hive table schemas using partitioning and bucketing to store tables as both external and internal table.  
•	Worked on developing Hive UDF’s in Python to define custom analytical functions.  
•	Worked on performance tuning, debugging and optimization of hive queries by changing the default YARN values.  
  
##What are the kind of tables used in Hive?Why?  
Hive has a relational database on the master node it uses to keep track of state. For instance, when you CREATE TABLE FOO(foo string) LOCATION 'hdfs://tmp/';, this table schema is stored in the database.  
External table- When you want for Data retrival after droping the table.  when external table is declared, default table path is changed to specified location in hive. When you drop an external table, it only drops the meta data but not the Data.<br />
Internal table- to add data to the already exsiting table. When you drop an internal table, it drops the data, and it also drops the metadata.<br />
  
##Partioning External Table in Hive?  
Has creating a external table involves changing of the Default Table Data path, we need add each partion manullay using Alter Table command. ALTER TABLE user ADD PARTITION(date='2010-02-22') to update the metadata in Hive metastore.  
  
Turning Hive queries?(Small table, Big table, Distributed cache)<br />
Turning hive for performance and optimization involves changing default yarn parameters. Like  
For over coming Java HeapDumpOnOutOfMemoryError:  
set mapreduce.map.memory.mb=12288;  
set mapreduce.map.java.opts= -Xmx8192M -verbose:gc -XX:+UseParNewGC -XX:+UseConcMarkSweepGC -XX:CMSInitiatingOccupancyFraction=70;  
To Optimise the a multiple Map-Reduce jobs:  
SET hive.exec.compress.output=true;  
SET io.seqfile.compression.type=BLOCK;  
To enable bucketing in hive:(Not needed form Hive 2.X)  
set hive.enforce.bucketing = true;  
To create avro file:  
set hive.exec.compress.output=true;  
set avro.output.codec=snappy;  

##What is Partioning and bucketing in hive & Partionting and Bucketing difference?<br />
Partioning of Hive tables can result in unknown number of Directories in Hive default Table storge path, depending on the Cloumns used.Partitioning data is often used for distributing load horizontally, this has performance benefit, and helps in organizing data in a logical fashion.  
  
Bucketing is another technique for decomposing data sets into more manageable parts in each Hive_Table Partition. Records with the same Column_value will always be stored in the same bucket. Hive can create a logically correct sampling. Bucketing also aids in doing efficient map-side joins and will be stored in a given number of Buckets specified in the Query.

set hive.enforce.bucketing = true;  
create table IF NOT EXISTS hotelhodsrrequest_PCCparsing_scala_Partitioned_and_Bucketed (PCC String, PropertyCode String, Duplication_Counts int)  
partitioned by (Year String, Month String)  
CLUSTERED BY (PCC) INTO 20 BUCKETS;  
  
INSERT OVERWRITE TABLE hotelhodsrrequest_PCCparsing_scala_Partitioned_and_Bucketed partition (Year, Month)  
SELECT hotelhodsrrequest_pccparsing_scala.pcc as PCC,  
hotelhodsrrequest_pccparsing_scala.propertycode as PropertyCode,  
hotelhodsrrequest_pccparsing_scala.duplication_counts as Duplication_Counts,  
hotelhodsrrequest_pccparsing_scala.year as Year,  
hotelhodsrrequest_pccparsing_scala.month as Month  
FROM hotelhodsrrequest_PCCparsing_scala;  
  
##Hive Queries:-<br />
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
A block is read in the form of a key-value pair in TextInputFormat, where the key is the byte offset of a line and the value is content of the line itself. Each block is considered as an InputSplit and a single Mapper is lauched for each inputSplit.  
  
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
  
  
Regular expressions in hive?  
When to use map and flat map in spark?  
map for each Tuple or row level operations.  
flat map for whole document level operations.  
  
  
Use of Some() KeyWord in Scala?  
def toInt(in: String): Option[Int] = {  
    try {  
        Some(Integer.parseInt(in.trim))  
    } catch {  
        case e: NumberFormatException => None  
    }  
}  
toInt(someString) match {  
    case Some(i) => println(i)  
    case None => println("That didn't work.")  
}  
Used to better handle the exception errors. Can be used to return some other value besides null, in this case, perhaps zero or some other meaningless number.  
  
How to Import and export Data using Sqoop?  
What is a Sparse Vector?  
A sparse vector has two parallel arrays –one for indices and the other for values. These vectors are used for storing non-zero entries to save space.  
What is RDD?  
RDDs (Resilient Distributed Datasets) are basic abstraction in Apache Spark that represent the data coming into the system in object format. RDDs are used for in-memory computations on large clusters, in a fault tolerant manner. RDDs are read-only portioned, collection of records, that are –  
Immutable – RDDs cannot be altered.  
Resilient – If a node holding the partition fails the other node takes the data.  
Explain about transformations and actions in the context of RDDs?  
Transformations are functions executed on demand, to produce a new RDD. All transformations are followed by actions. Some examples of transformations include map, filter and reduceByKey.  
Actions are the results of RDD computations or transformations. After an action is performed, the data from RDD moves back to the local machine. Some examples of actions include reduce, collect, first, and take.  

How can you minimize data transfers when working with Spark?  
Minimizing data transfers and avoiding shuffling helps write spark programs that run in a fast and reliable manner. The various ways in which data transfers can be minimized when working with Apache Spark are:  
Using Broadcast Variable- Broadcast variable enhances the efficiency of joins between small and large RDDs.  
Using Accumulators – Accumulators help update the values of variables in parallel while executing.  
The most common way is to avoid operations ByKey, repartition or any other operations which trigger shuffles.  
What is a DStream?
Discretized Stream is a sequence of Resilient Distributed Databases that represent a stream of data. DStreams can be created from various sources like Apache Kafka, HDFS, and Apache Flume. DStreams have two operations –  
Transformations that produce a new DStream.  
Output operations that write data to an external system.  
What is the advantage of a Parquet file?  
Parquet file is a columnar format file that helps –  
Limit I/O operations  
Consumes less space  
Fetches only required columns.  
What do you understand by Pair RDD?  
Special operations can be performed on RDDs in Spark using key/value pairs and such RDDs are referred to as Pair RDDs. Pair RDDs allow users to access each key in parallel. They have a reduceByKey () method that collects data based on each key and a join () method that combines different RDDs together, based on the elements having the same key.  
Explain about the different types of transformations on DStreams?  
Stateless Transformations- Processing of the batch does not depend on the output of the previous batch. Examples – map (), reduceByKey (), filter ().  
Stateful Transformations- Processing of the batch depends on the intermediary results of the previous batch. Examples –Transformations that depend on sliding windows.  
How can you remove the elements with a key present in any other RDD?  
Use the subtractByKey () function  
What is the difference between persist() and cache()?   
persist () allows the user to specify the storage level whereas cache () uses the default storage level.  
What are the various levels of persistence in Apache Spark?  
Apache Spark automatically persists the intermediary data from various shuffle operations, however it is often suggested that users call persist () method on the RDD in case they plan to reuse it. Spark has various persistence levels to store the RDDs on disk or in memory or as a combination of both with different replication levels.  
The various storage/persistence levels in Spark are -  
MEMORY_ONLY  
MEMORY_ONLY_SER  
MEMORY_AND_DISK  
MEMORY_AND_DISK_SER, DISK_ONLY  
OFF_HEAP  
Hadoop uses replication to achieve fault tolerance. How is this achieved in Apache Spark?  
Data storage model in Apache Spark is based on RDDs. RDDs help achieve fault tolerance through lineage. RDD always has the information on how to build from other datasets. If any partition of a RDD is lost due to failure, lineage helps build only that particular lost partition.  
Explain about the core components of a distributed Spark application.  
Driver- The process that runs the main () method of the program to create RDDs and perform transformations and actions on them.  
Executor –The worker processes that run the individual tasks of a Spark job.  
Cluster Manager-A pluggable component in Spark, to launch Executors and Drivers. The cluster manager allows Spark to run on top of other external managers like Apache Mesos or YARN.  
What do you understand by Executor Memory in a Spark application?  
Every spark application has same fixed heap size and fixed number of cores for a spark executor. The heap size is what referred to as the Spark executor memory which is controlled with the spark.executor.memory property of the –executor-memory flag. Every spark application will have one executor on each worker node. The executor memory is basically a measure on how much memory of the worker node will the application utilize.  
What are the disadvantages of using Apache Spark over Hadoop MapReduce?  
Apache spark does not scale well for compute intensive jobs and consumes large number of system resources. Apache Spark’s in-memory capability at times comes a major roadblock for cost efficient processing of big data. Also, Spark does have its own file management system and hence needs to be integrated with other cloud based data platforms or apache hadoop.  
 What do you understand by SchemaRDD?  
An RDD that consists of row objects (wrappers around basic string or integer arrays) with schema information about the type of data in each column.  
Define a worker node.  
A node that can run the Spark application code in a cluster can be called as a worker node. A worker node can have more than one worker which is configured by setting the SPARK_ WORKER_INSTANCES property in the spark-env.sh file. Only one worker is started if the SPARK_ WORKER_INSTANCES property is not defined.  
  
#4th Interview  
Explain Specific Streaming process and saving files to HDFS in SparkStreaming with Kafka?  
Explain Cassandra Arcitecture and timeStamps methods in it?  
What is a lineage Map in Spark?  
Why the Data needs to serialised in Spark?  
Differences in Spark Deployment mode(yarn-cluster and yarn-client mode)?  
Adding other jars(thrid party) in spark when execution in spark-submit?  
How to enable Speculative execution in Spark?  
Different join methods in Hive(using distributed Chace)?  
Difference between an RDD and DataFrame?  
Does sqoop launches only mapper? Yes  
What are broadcast and Accumulator variables in Spark?  
