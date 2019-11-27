## General Description
- Hive is a framework that provides a SQL-like interface to various databases and file systems (specifically built for HBase/HDFS)
- Hive is integrated with Hadoop
- Hive Hadoop refers to the Hive framework integrated with HBase
- Essentially, Hive represents SQL-like operations, known as HiveQL/HQL, which translate to pre-implemented MapReduce jobs 
- Both Hive and Pig are components of the Hadoop ecosystem that try to ease the complexity of writing complex java-based MapReduce programs in order to analyze the data stores in the HDFS (or some other file system)

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
