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
  
#MapReduce  
#Spark  
##SparkCore
##SparkSQL
##SparkStreaming
#Hive and Impala  
#Comparision  
