## General Description
- Spark is a distributed computing (or data processing) engine
- Spark represents its core processing engine, along with the following other features integrated into the processing engine:
	- Spark SQL
	- Spark Streaming
	- MLlib
	- GraphX
- A large percentage of Spark's speed comes from storing data in-memory (which allows Spark to rapidly run repeated queries)
- We are able to run Spark on server-side clusters

## Relevant Spark APIs
- Spark SQL is an API that lets you query structured data inside Spark programs, using either SQL or a familiar DataFrame API
	- DataFrames and SQL provide a common way to access a variety of data sources, including Hive, Avro, Parquet, ORC, JSON, and JDBC
- Spark Streaming is an API that lets you write streaming jobs the same way you would write batch jobs
	- This typically refers to the data engineering tasks
	- Supports Java, Scala, and Python
	- Spark Streaming can read data from HDFS, Flume, Kafka, Twitter, ZeroMQ, and custom data sources
	- Spark Streaming uses Zookeeper and HDFS for deploying streaming applications in production
- MLlib is Spark's machine learning API
	- This typically refers to the data science tasks
	- Supports Java, Scala, Python, and R
	- MLlib represents an alternative to slow and overly complicated MapReduce jobs
	- MLlib allows data scientists to transform, process data, and run algorithms nearly 100 times faster than MapReduce
	- MLlib contains many algorithms and utilities, such as classification methods, gradient-boosted trees, k-means clustering, etc.
- GraphX is Spark's API involves graph-parallel computation to display and work with graphics
	- GraphX unifies ETL, exploratory analysis, and iterative graph computation within a single API system
	- GraphX lets you view the same data as both graphs and collections, transformed and joined graphs, with RDDs efficiently
	- GraphX allows you to write custom iterative graph algorithms using the Pregel API
	- GraphX offers comparable performance to the fastest specialized graph processing systems, such as GraphLab and Giraph

## Achievements of Spark
- Spark is a unified framework that attempts to provide Data Engineers with the tools to perform ETL and SQL batch jobs, and Data Scientists with the tools to perform machine learning and model training on large datasets
- Spark provides stream processing capabilities, such as processing log files or sensor data that are constantly being exported into our database
- Spark provides machine learning capabilities, such as running broadly similar queries on large data that is stored in memory
- Spark provides interactive analytical capabilties, such as querying data, viewing the results, and altering the original query again and again to create dynamic dashboards
- Spark provides data integration capabilities, such as performing ETL jobs

## Benefits of Spark over MapReduce
- Spark executes much faster by caching data in memory across multiple parallel operations, whereas MapReduce involves more reading and writing from disk
- Spark runs multi-threaded tasks inside of JVM processes, whereas MapReduce runs heavier weight tasks inside of JVM processes
	- This gives Spark faster startup, better parallelism, and better CPI utilization
- Spark provides a richer functional programming model than MapReduce
- Spark is especially useful for parallel processing of distributed data with iterative algorithms

## References
- https://mapr.com/blog/spark-101-what-it-what-it-does-and-why-it-matters/
- https://spark.apache.org/sql/
- https://spark.apache.org/streaming/
- https://spark.apache.org/mllib/
- https://spark.apache.org/graphx/
