#General  
  
###Brief the resume?  
I’m a Hadoop Developer with hands on experience in performing Data Analytics using Hadoop components like Spark, SparkSQL, Spark-Streaming, Hive and Impala with in-depth understanding of Hadoop Map-reduce and distributed file systems architecture. I have mainly worked on Parsing, filtering and Manipulating different kinds of Semi-Structured, Unstructured and Structured data.  
  
My most recent project is at Sabre in Southlake TX, which is the largest Global Distribution Systems provider for air bookings in North America. Sabre processes more than 1.5 billion daily API requests. The systems should quickly cull through billions of possibilities to return the most appropriate itineraries to travel shoppers. Data from these data points coming through travel agencies could be structured and unstructured in few cases. All this data was collected, aggregated and analyzed in the Hadoop clusters to find customer usage patterns which helps make cross sell, up sell business decisions and device targeted marketing strategies.  
  
###Few tasks you have done at your most recent project?  
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
  
###Describe the Arcitecture at your Organisation?  
<p align="center">
  <img src="https://www.dropbox.com/s/3heoh2vsif84mgv/Oracle_Big_Data_Sloution.png?raw=1" width="650"/>
  <img src="https://www.dropbox.com/s/3heoh2vsif84mgv/Oracle_Big_Data_Sloution.png?raw=1" width="650"/>
</p>
  
From the website they are two outgoing data streams one is into Cassandra, where the few required data attributes are processed and loaded back to the Website in real time. Other, is through the Data-pipeline of Apache Kafka and Spark Streaming, where all the WebLogs of site activity was collected in near real time streaming and stored in HDFS.  
  
The Data collected in HDFS is Processed using Hive, Impala and Spark to Load Recomendations into Cassandra (or) to push Data into Backend DataBases and Relational DataBases like R and Vertica for analytical purposes (or) to push the data into Legacy Databases like MySQL.  
  
###Descibe why is it neccessary for Enterprices to have both NoSQL and Hadoop components in it for Data processing?  
The ability to extract information from operational data in real time is critical for a modern, agile enterprise. The faster you can harness insights from data, the greater your advantage in driving revenue, reducing costs, and increasing efficiency. Modern architecture for real time big data combines Hadoop and NoSQL. Hadoop is engineered for big data analytics, but it’s not real time. NoSQL is engineered for real-time big data, but it’s operational rather than analytical. NoSQL together with Hadoop is the key to real time big data.  
  
###What are operational and analytical operations?  
Operational Data  
A company's operations are supported by applications that automate key business processes. These include areas such as sales, service, order management, manufacturing, purchasing, billing, accounts receivable and accounts payable. These applications require significant amounts of data to function correctly.  This includes data about the objects that are involved in transactions, as well as the transaction data itself.  For example, when a customer buys a product, the transaction is managed by a sales application.  The objects of the transaction are the Customer and the Product.  The transactional data is the time, place, price, discount, payment methods, etc. used at the point of sale. The transactional data is stored in On-Line Transaction Processing (OLTP) tables that are designed to support high volume low latency access and update.  
  
Master Data Management(MDM) solutions that focus on managing operational master data supporting transactional applications are called Operational MDM. They rely heavily on integration technologies. They bring real value to the enterprise, but lack the ability to influence reporting and analytics.  
  
Operational Big Data systems provide operational features to run real-time, interactive workloads that ingest and store data. Cassandra is a top technology for operational Big Data applications with over 10 million downloads of its open source software.  
  
Analytical Data  
Analytical data is used to support a company's decision making.  Customer buying patterns are analyzed to identify churn, profitability, and marketing segmentation. Suppliers are categorized, based on performance characteristics over time, for better supply chain decisions. Product behavior is scrutinized over long periods to identify failure patterns.  This data is stored in large Data Warehouses and possibly smaller data marts with table structures designed to support heavy aggregation, ad hoc queries, and data mining. Typically the data is stored in large fact tables surrounded by key dimensions such as customer, product, supplier, account, and location.  
  
Master Data Management(MDM) solutions that focus on managing analytical master data are called Analytical MDM. They focus on providing high quality dimensions with their multiple simultaneous hierarchies to data warehousing and BI technologies. They also bring real value to the enterprise, but lack the ability to influence operational systems. Any data cleansing done inside an Analytical MDM solution is invisible to the transactional applications and transactional application knowledge is not available to the cleansing process. Because Analytical MDM systems can do nothing to improve the quality of the data under the heterogeneous application landscape, poor quality inconsistent domain data finds its way into the BI systems and drives less than optimum results for reporting and decision making.  
  
Analytical Big Data technologies, on the other hand, are useful for retrospective, sophisticated analytics of your data. Hadoop is the most popular example of an Analytical Big Data technology.  
  
###How WebLog and Transaction information to be processed by Big Data is Generated(Data Sources People(Social Media), Machines(WebLogs), Organisation(Transactions))?  
###Yarn Resources and peformane tuning?  
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
###Tablue data vizulalization?  
###Difference between object, method, functions and classes in Java?(Objects are instances of classes, whose class Functions can be acssed as methods)  
###Difference between public, private and default value decrelation in Java?  
###is val and var public, private and default decrelation in Scala?  
###Use of Some() KeyWord in Scala?  
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
###deceralation of public, private and default types in python?  
###Changing file permissions in Shell Scripting?  
###What is DML and DDL?  
DML is abbreviation of Data Manipulation Language. It is used to retrieve, store, modify, delete, insert and update data in database.
Examples: SELECT, UPDATE, INSERT statements  
  
DDL is abbreviation of Data Definition Language. It is used to create and modify the structure of database objects in database.
Examples: CREATE, ALTER, DROP statements  
###Primary key vs unique key in SQL?  
Primary Key:  
Can be only one in a table  
In some DBMS it cannot be NULL - e.g. MySQL adds NOT NULL  
Primary Key is a unique key identifier of the record  
Unique Key:  
Can be more than one unique key in one table  
Unique key can have null values  
It can be a candidate key  
Unique key can be null and may not be unique  
###What is the advantage of a Parquet file?  
Parquet file is a columnar format file that helps –  
Limit I/O operations  
Consumes less space  
Fetches only required columns.  
###Difference between a Data Engineer, Data Analyst and Data Scientist?  
###Type of Analytics Done on Big Data?   
Descriptive Analytics: If you just told me that you spent 25% on food, 35% on clothing, 20% on entertainment and the rest on miscellaneous items last year using your credit card, that is descriptive analytics. Of course, you can go into lot more detail as well.
  
  
Predictive Analytics: If you analyzed your credit card history for the past 5 years and the split is somewhat consistent, you can safely forecast with high probability that next year will be similar to past years. The fine print here is that this is not about ‘predicting the future’ rather ‘forecasting with probabilities’ of what might happen. In Big data predictive analytics, data scientists may use advanced techniques like data mining, machine learning, and advanced statistical processes (we’ll discuss all these terms later) to forecast weather, economy etc.  
  
Prescriptive Analytics: Still using the credit card transactions example, you may want to find out which spending to target (i.e. food, entertainment, clothing etc.) to make a huge impact on your overall spending. Prescriptive analytics builds on predictive analytics by including ‘actions’ (i.e. reduce food or clothing or entertainment) and analyzing the resulting outcomes to ‘prescribe’ the best category to target to reduce your overall spend. You can extend this to big data and imagine how executives can make data-driven decisions by looking at the impacts of various actions in front of them.  
  
  
#MapReduce  
  
###Map/reduce if 1st file had empId and empName & 2nd file empId and empSalary. How to find the max salary empId? How many mappers are launched?(Partially Unawnsered)  
A block is read in the form of a key-value pair in TextInputFormat, where the key is the byte offset of a line and the value is content of the line itself. Each block is considered as an InputSplit and a single Mapper is lauched for each inputSplit.  
###Explaine Map/Reduce process?  
  
  
#Spark  
  
##SparkCore  
###Difference between Map-reduce and spark? Advantages and disadvantages and execution methods?  
Conceptually DAG model is a strict generalization of MapReduce model. DAG-based systems like Spark and Tez that are aware of the whole DAG of operations can do better global optimizations than systems like Hadoop MapReduce which are unaware of the DAG to be executed.  
  
<p align="center">
  <img src="https://www.dropbox.com/s/99ctmul7unk6wvk/Map-Reduce.png?raw=1" width="650"/>
  <img src="https://www.dropbox.com/s/8uw8f0ieu4uuqgi/Spark.jpg?raw=1" width="650"/>
</p>
  
Conceptually speaking, the MapReduce model simply states that distributed computation on a large dataset can be boiled down to two kinds of computation steps - a map step and a reduce step. One pair of map and reduce does one level of aggregation over the data. Complex computations typically require multiple such steps. When you have multiple such steps, it essentially forms a DAG of operations. So a DAG execution model is essentially a generalization of the MapReduce model.  
  
While this is the theory, different systems implement this theory in different ways, and that is where the "advantages" and "disadvantages" come from. Computations expressed in Hadoop MapReduce boil down to multiple iterations of (i) read data from HDFS, (ii) apply map and reduce, (iii) write back to HDFS. Each map-reduce round is completely independent of each other, and Hadoop does not have any global knowledge of what MR steps are going to come after each MR. For many iterative algorithms this is inefficient as the data between each map-reduce pair gets written and read from filesystem. Newer systems like Spark and Tez improves performance over Hadoop by considering the whole DAG of map-reduce steps and optimizing it globally (e.g., pipelining consecutive map steps into one, not write intermediate data to HDFS). This prevents writing data back and forth after every reduce.  
  
Storm, being a streaming system, is slightly different from the batch processing systems referred earlier. It also sets up a DAG of nodes lets the records stream between the nodes. Its best to compare Storm with Spark Streaming (streaming system built over Spark) than Hadoop MapReduce. Both accepts a DAG of operations representing the streaming computation, but then process the DAG in slightly different ways. Storm sets up a DAG of node and allocates each operation in the DAG of ops to different nodes. Spark Streaming does not pre-allocate, rather uses the underlying Spark's mechanisms to dynamically allocate tasks to available resources. This gives different kinds of performance characteristics.  
###What are the disadvantages of using Apache Spark over Hadoop MapReduce?  
Apache spark does not scale well for compute intensive jobs and consumes large number of system resources. Apache Spark’s in-memory capability at times comes a major roadblock for cost efficient processing of big data. Also, Spark does have its own file management system and hence needs to be integrated with other cloud based data platforms or apache hadoop.  
###Define a worker node?  
A node that can run the Spark application code in a cluster can be called as a worker node. A worker node can have more than one worker which is configured by setting the SPARK_ WORKER_INSTANCES property in the spark-env.sh file. Only one worker is started if the SPARK_ WORKER_INSTANCES property is not defined.  
###What is a lineage Map in Spark?  
###Explain about the core components of a distributed Spark application?  
Driver- The process that runs the main () method of the program to create RDDs and perform transformations and actions on them.  
Executor –The worker processes that run the individual tasks of a Spark job.  
Cluster Manager-A pluggable component in Spark, to launch Executors and Drivers. The cluster manager allows Spark to run on top of other external managers like Apache Mesos or YARN.  
###What do you understand by Executor Memory in a Spark application?  
Every spark application has same fixed heap size and fixed number of cores for a spark executor. The heap size is what referred to as the Spark executor memory which is controlled with the spark.executor.memory property of the –executor-memory flag. Every spark application will have one executor on each worker node. The executor memory is basically a measure on how much memory of the worker node will the application utilize.  
###How to enable speculative execution in spark?  
spark-submit \  
--conf "spark.speculation=true" \  
--conf "spark.speculation.multiplier=5" \  
--conf "spark.speculation.quantile=0.90" \  
--class "org.asyncified.myClass" "path/to/uberjar.jar"  
###Differences in Spark Deployment mode(yarn-cluster and yarn-client mode)?  
###Adding other jars(thrid party) in spark when execution in spark-submit?  
###How can you minimize data transfers when working with Spark?  
Minimizing data transfers and avoiding shuffling helps write spark programs that run in a fast and reliable manner. The various ways in which data transfers can be minimized when working with Apache Spark are:  
Using Broadcast Variable- Broadcast variable enhances the efficiency of joins between small and large RDDs.  
Using Accumulators – Accumulators help update the values of variables in parallel while executing.  
The most common way is to avoid operations ByKey, repartition or any other operations which trigger shuffles.  
###Hadoop uses replication to achieve fault tolerance. How is this achieved in Apache Spark?  
Data storage model in Apache Spark is based on RDDs. RDDs help achieve fault tolerance through lineage. RDD always has the information on how to build from other datasets. If any partition of a RDD is lost due to failure, lineage helps build only that particular lost partition.  
###Why is Spark conf and spark context related to the program?  
###What is an RDD in spark?(Partially anwsred look in Chapter 3 Spark Data Analytics cook book)  
RDDs (Resilient Distributed Datasets) are basic abstraction in Apache Spark that represent the data coming into the system in object format. RDDs are used for in-memory computations on large clusters, in a fault tolerant manner. RDDs are read-only portioned, collection of records, that are –  
Immutable – RDDs cannot be altered.  
Resilient – If a node holding the partition fails the other node takes the data.  
###Why the Data needs to serialised in Spark?  
###Difference between action and transformation?  
###When to use map and flat map in spark?  
map for each Tuple or row level operations.  
flat map for whole document level operations.  
###What is a Sparse Vector?  
A sparse vector has two parallel arrays –one for indices and the other for values. These vectors are used for storing non-zero entries to save space.  
###UDFs in Spark?  
###What do you understand by Pair RDD?  
Special operations can be performed on RDDs in Spark using key/value pairs and such RDDs are referred to as Pair RDDs. Pair RDDs allow users to access each key in parallel. They have a reduceByKey () method that collects data based on each key and a join () method that combines different RDDs together, based on the elements having the same key.  
###Differences in Spark Deployment mode(yarn-cluster and yarn-client mode)?  
###Adding other jars(thrid party) in spark when execution in spark-submit?  
###What are broadcast and Accumulator variables in Spark?  
  
##SparkSQL  
###Difference between an RDD and DataFrame?  
###What do you understand by SchemaRDD?  
An RDD that consists of row objects (wrappers around basic string or integer arrays) with schema information about the type of data in each column.  
###Case class in SparkSQL?  
###Data preparation methods in SparkSQL?(Chapter 3 Spark Data Analytics cook book)  
###How can you remove the elements with a key present in any other RDD?  
Use the subtractByKey () function  
  
##SparkStreaming  
###Explain the Process of Spark Streaming?  
###What is a DStream?  
Discretized Stream is a sequence of Resilient Distributed Databases that represent a stream of data. DStreams can be created from various sources like Apache Kafka, HDFS, and Apache Flume. DStreams have two operations –  
Transformations that produce a new DStream.  
Output operations that write data to an external system.  
###Explain about the different types of transformations on DStreams?  
Stateless Transformations- Processing of the batch does not depend on the output of the previous batch. Examples – map (), reduceByKey (), filter ().  
Stateful Transformations- Processing of the batch depends on the intermediary results of the previous batch. Examples –Transformations that depend on sliding windows.  
###What is the difference between persist() and cache()?  
persist () allows the user to specify the storage level whereas cache () uses the default storage level.  
###What are the various levels of persistence in Apache Spark?  
Apache Spark automatically persists the intermediary data from various shuffle operations, however it is often suggested that users call persist () method on the RDD in case they plan to reuse it. Spark has various persistence levels to store the RDDs on disk or in memory or as a combination of both with different replication levels.  
The various storage/persistence levels in Spark are -  
MEMORY_ONLY  
MEMORY_ONLY_SER  
MEMORY_AND_DISK  
MEMORY_AND_DISK_SER, DISK_ONLY  
OFF_HEAP  
###Explain Specific Streaming process and saving files to HDFS in SparkStreaming with Kafka?  
###How to create Streams for Basic Input SOurces like file and Socket & Advanced Sources like Kafka, Twitter and Flume?  
  
  
#Hive and Impala  
  
###Difference between Impala and Hive?  
###Disadvantages of Impala?(speculative execution)  
###What are the kind of tables used in Hive?Why?  
Hive has a relational database on the master node it uses to keep track of state. For instance, when you CREATE TABLE FOO(foo string) LOCATION 'hdfs://tmp/';, this table schema is stored in the database.  
External table- When you want for Data retrival after droping the table. when external table is declared, default table path is changed to specified location in hive. When you drop an external table, it only drops the meta data but not the Data. 
Internal table- to add data to the already exsiting table. When you drop an internal table, it drops the data, and it also drops the metadata.  
###What is Partioning and bucketing in hive & Partionting and Bucketing difference?  
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
###Partioning External Table in Hive?  
Has creating a external table involves changing of the Default Table Data path, we need add each partion manullay using Alter Table command. ALTER TABLE user ADD PARTITION(date='2010-02-22') to update the metadata in Hive metastore.  
###DIfference between where and having clauses?  
HAVING is used to check conditions after the aggregation takes place.  
WHERE is used before the aggregation takes place.  
The HAVING clause was added to SQL because the WHERE keyword could not be used with aggregate functions.  
###How many mapper will "select * from Data" launch?  
No Mapper & No Reducer  
###Does "where = """ launch Mapper or reducers?  
Mappers only  
###Does "Group by = """ launch Mapper or reducers?  
Reducer only
###UDF's in Hive and Hwo do you Implement it and How to load UDF's in Hive?  
###Invalidate metaData command in Impala?  
###How to change default Heap Dump memory parameters in Hive using set command?  
###Difference between Map side and reduce side joins?  
###Difference between GroupBy, OrderBy, sortBy, DISTRIBUTE BY and CLUSTER BY x?  
GroupBy=> Aggregates the Data into groups like using SUM, Avg etc.. on a cloumn. The GROUP BY clause’s purpose is summarize unique combinations of columns values. Often group by is followed by order by or cluster by cluases.  
ORDER BY guarantees global ordering, but does this by pushing all data through just one reducer. This is basically unacceptable for large datasets. You end up one sorted file as output.  
SORT BY x: orders data at each of N reducers, but each reducer can receive overlapping ranges of data. You end up with N or more sorted files with overlapping ranges.  
DISTRIBUTE BY x: ensures each of N reducers gets non-overlapping ranges of x, but doesn't sort the output of each reducer. You end up with N or unsorted files with non-overlapping ranges.  
CLUSTER BY x: ensures each of N reducers gets non-overlapping ranges, then sorts by those ranges at the reducers. This gives you global ordering, and is the same as doing (DISTRIBUTE BY x and SORT BY x). You end up with N or more sorted files with non-overlapping ranges.
So CLUSTER BY is basically the more scalable version of ORDER BY.  
###Regular expressions in hive?  
###Different join methods in Hive(using distributed Chace) and turning Hive queries for Small table, Big table using Distributed cache?   
  
  
#Sqoop  
###How to Import and export Data using Sqoop?  
###Does sqoop launches only mapper?  
Yes, Sqoop lauches only Mappers to import and Export Data.  
  
  
#HDFS  
###What is splittablity and block compression and How does it effects different file formats like CSV, JSON, XML, AVRO and Parquet?  
###Falut Tolerence and high availability in HDFS?(Replication and Speculative execution)  
  
  
#Cassandra   
###Explain Cassandra Arcitecture and timeStamps methods in it?  
