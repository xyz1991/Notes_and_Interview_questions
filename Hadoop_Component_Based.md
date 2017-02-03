#General
  
##Brief the resume?  
I’m a Hadoop Developer with hands on experience in performing Data Analytics using Hadoop components like Spark, SparkSQL, Spark-Streaming, Hive and Impala with in-depth understanding of Hadoop Map-reduce and distributed file systems architecture. I have mainly worked on Parsing, filtering and Manipulating different kinds of Semi-Structured, Unstructured and Structured data.  
  
My most recent project is at Sabre in Southlake TX, which is the largest Global Distribution Systems provider for air bookings in North America. Sabre processes more than 1.5 billion daily API requests. The systems should quickly cull through billions of possibilities to return the most appropriate itineraries to travel shoppers. Data from these data points coming through travel agencies could be structured and unstructured in few cases. All this data was collected, aggregated and analyzed in the Hadoop clusters to find customer usage patterns which helps make cross sell, up sell business decisions and device targeted marketing strategies.  
  
##Few tasks you have done at your most recent project?  
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
  
##Describe the Arcitecture at your Organisation?  
<p align="center">
  <img src="https://www.dropbox.com/s/3heoh2vsif84mgv/Oracle_Big_Data_Sloution.png?raw=1" width="650"/>
  <img src="https://www.dropbox.com/s/3heoh2vsif84mgv/Oracle_Big_Data_Sloution.png?raw=1" width="650"/>
</p>
  
From the website they are two outgoing data streams one is into Cassandra, where the few required data attributes are processed and loaded back to the Website in real time. Other, is through the Data-pipeline of Apache Kafka and Spark Streaming, where all the WebLogs of site activity was collected in near real time streaming and stored in HDFS.  
  
The Data collected in HDFS is Processed using Hive, Impala and Spark to Load Recomendations into Cassandra (or) to push Data into Backend DataBases and Relational DataBases like R and Vertica for analytical purposes (or) to push the data into Legacy Databases like MySQL.  
