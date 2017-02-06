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
###Tablue data vizulalization?  
###Difference between object, method, functions and classes in Java?(Objects are instances of classes, whose class Functions can be acssed as methods)  
###Difference between public, private and default value decrelation in Java?  
###is val and var public, private and default decrelation in Scala?  
###Use of Some() KeyWord in Scala?  
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
###What is the advantage of a Parquet file?(A)  
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
  
###Map/reduce if 1st file had empId and empName & 2nd file empId and empSalary. How to find the max salary empId? How many mappers are launched?(A)  
###Explaine Map/Reduce process?  
  
  
#Spark  
  
##SparkCore  
###Difference between Map-reduce and spark? Advantages and disadvantages and execution methods?(A)  
###What are the disadvantages of using Apache Spark over Hadoop MapReduce?(A)  
###Define a worker node?(A)  
###What is a lineage Map in Spark?  
###Explain about the core components of a distributed Spark application?(A)  
###What do you understand by Executor Memory in a Spark application?(A)  
###How to enable speculative execution in spark?(A)  
###Differences in Spark Deployment mode(yarn-cluster and yarn-client mode)?  
###Adding other jars(thrid party) in spark when execution in spark-submit?  
###How can you minimize data transfers when working with Spark?(A)  
###Hadoop uses replication to achieve fault tolerance. How is this achieved in Apache Spark?(A)  
###Why is Spark conf and spark context related to the program?  
###What is an RDD in spark?(Chapter 3 Spark Data Analytics cook book)(A)  
###Why the Data needs to serialised in Spark?  
###Difference between action and transformation?  
###When to use map and flat map in spark?(A)  
###What is a Sparse Vector?(A)  
###UDFs in Spark?  
###What do you understand by Pair RDD?(A)  
###Differences in Spark Deployment mode(yarn-cluster and yarn-client mode)?  
###Adding other jars(thrid party) in spark when execution in spark-submit?  
###What are broadcast and Accumulator variables in Spark?  
  
##SparkSQL  
###Difference between an RDD and DataFrame?  
###What do you understand by SchemaRDD?(A)  
###Case class in SparkSQL?  
###Data preparation methods in SparkSQL?(Chapter 3 Spark Data Analytics cook book)  
###How can you remove the elements with a key present in any other RDD?(A)  
  
##SparkStreaming  
###Explain the Process of Spark Streaming?  
###What is a DStream?(A)  
###Explain about the different types of transformations on DStreams?(A)  
###What is the difference between persist() and cache()?(A)  
###Explain Specific Streaming process and saving files to HDFS in SparkStreaming with Kafka?  
###How to create Streams for Basic Input SOurces like file and Socket & Advanced Sources like Kafka, Twitter and Flume?  
  
  
#Hive and Impala  
  
###Difference between Impala and Hive?  
###Disadvantages of Impala?(speculative execution)  
###What are the kind of tables used in Hive?Why?(A)  
###What is Partioning and bucketing in hive & Partionting and Bucketing difference?(A)  
###Partioning External Table in Hive?(A)  
###DIfference between where and having clauses?(A)  
###select * from Data?(A)  
###where = "" ?(A)  
###Group by = "" ?(A)  
###UDF's in Hive and Hwo do you Implement it and How to load UDF's in Hive?  
###Invalidate metaData command in Impala?  
###How to change default Heap Dump memory parameters in Hive using set command?  
###Difference between Map side and reduce side joins?  
###Difference between GroupBy, OrderBy, sortBy, DISTRIBUTE BY and CLUSTER BY x?(A)  
###Regular expressions in hive?  
###Different join methods in Hive(using distributed Chace)?  
  
  
#Sqoop  
###How to Import and export Data using Sqoop?  
###Does sqoop launches only mapper? Yes  
  
  
#HDFS  
###What is splittablity and block compression and How does it effects different file formats like CSV, JSON, XML, AVRO and Parquet?
###Falut Tolerence and high availability in HDFS?(Replication and Speculative execution)  
  
  
#Cassandra   
###Explain Cassandra Arcitecture and timeStamps methods in it?  

