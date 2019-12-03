## General Description
- Hive is a framework that provides a SQL-like interface to various databases and file systems (specifically built for HBase/HDFS)
- Hive is integrated with Hadoop
- Hive Hadoop refers to the Hive framework integrated with HBase
- Essentially, Hive represents SQL-like operations, known as HiveQL/HQL, which translate to pre-implemented MapReduce jobs 
- Both Hive and Pig are components of the Hadoop ecosystem that try to ease the complexity of writing complex java-based MapReduce programs in order to analyze the data stores in the HDFS (or some other file system)

## Hive Tables and the Metastore
- The Hive Metastore is a relational database repository containing metadata about objects you create in Hive
- These objects are known as Hive tables
- Tables created in Hive (i.e. Hive tables) are just files stored in HDFS
- The only difference between files from HDFS and Hive tables is where the object is created (i.e. Hive tables are created in Hive and HDFS files are created in HDFS)
- When we create Hive tables, the table metadata is stored in the Hive Metastore
- The metadata includes some of the following information about the data:
	- Column names
	- Data types
	- Indexes
	- Comments
- We can access the Hive Metastore using ODBC and JDBC connections
- Obviously, we can access the HDFS (where the actual data is stored) using ODBC and JDBC connections

## Motivating Big Data Technologies
- When dealing with big data technologies, there are typically two general types of tools:
	1. Execution engines (required)
	2. Query Optimizers (optional)
- An execution engine is a framework that processes queries (or jobs) related to the data
- A query optimizer is a framework that optimizes queries before (or sometimes during) they are processed

## Hive and Spark
- Spark is a framework that contains its own execution engine and query optimizers, but it is known for its execution engine
- Hive is a framework that contains an execution engine and query optimizers, but it is known for its query optimizers
- Hive doesn't really have its own execution engine, since its default execution engine is just MapReduce
- Spark has its own execution engine
- Hive's query optimization plan is based on its Metastore, which represents relational tables containing metadata about the HDFS
- Spark's query optimization plan is based on its Catalyst Optimizer, which represents a programming model for rule-based optimization and cost-based optimization
- Hive typically sits on top of HDFS
	- In this case, we would use HDFS as our storage layer, Hive as our query optimization layer, and Hive as our execution engine layer (or we could say MapReduce is our execution engine layer, since Hive's default execution engine is MapReduce)
- Spark can sit on top of HDFS or Hive
	- In this case, we could use HDFS as our storage layer, Hive as our query optimization layer, and Spark as our execution engine layer
	- Or, we could just use HDFS as our storage layer, Spark as our query optimization layer, and Spark as our execution engine layer
	- Or, we could just use HDFS as our storage layer and Spark as our execution engine layer (without any query optimization layer)

## Differences between Hive and Pig
- Pig is a procedural language, whereas Hive is SQL-like language
- Pig is used when programming, whereas Hive is used for creating reports
- Pig is mainly used by researchers and programmers, whereas Hive is mainly used by data analysts
- Pig operates on the client side of a cluster, whereas Hive operates on the server side of a cluster
- Pig does not have a dedicated metadata database, whereas Hive makes use of exact variation of SQL DDL language by defining tables beforehand
- Pig is SQL-like but varies to a great extent, whereas Hive directly leverages SQL and is easy to learn for database users
- Pig supports Avro file formatting, whereas Hive does not support Avro file formatting

## References
- https://www.dezyre.com/article/difference-between-pig-and-hive-the-two-key-components-of-hadoop-ecosystem/79
- https://data-flair.training/blogs/apache-hive-architecture/
- https://en.wikipedia.org/wiki/Apache_Hive#HiveQL
- https://logz.io/blog/hive-vs-spark/
- https://spark.apache.org/docs/latest/sql-data-sources-hive-tables.html#interacting-with-different-versions-of-hive-metastore
- https://community.cloudera.com/t5/Support-Questions/How-the-hive-metastore-works/td-p/136619
