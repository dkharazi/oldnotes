## General Description
- ETL refers to the process of extracting, transforming, and loading data (respectively) into data lakes and data warehouses throughout the data pipeline
- ELT refers to the process of extracting, loading, and transforming (respectively) into data lakes and data warehouses throughout the data pipeline
- ETL jobs are typically performed using a Hadoop framwork and Hive (to provide a SQL-like interface)
- ELT jobs are typically performed using cloud services, such as AWS Redshift, and Spark

## Basic ETL Process
1. First, extract data from an external source (such as operational systems, third party APIs, RDBMS, etc.) into a data lake
2. Next, transform the data from the data lake
3. Then, load the transformed data either back into the data lake, or into a data warehouse

## Basic ELT Process
1. First, extract data from an external source (such as operational systems, third party APIs, RDBMS, etc.) into a data lake
2. Next, load the data from the data lake into a data warehouse
3. Then, transform the data in the data warehouse and load it back into the data warehouse somewhere

## Advantages of ETL
- No need to maintain any staging area tables/schemas within Redshift
- Possibility to spin a preconfigured Hadoop environment on AWS (on demand), with multiple cheap machines (i.e. spot instances) to do all computational intense transformations and shut down clusters after ETL is finished
- Easy scalability in both directions (adding or removing clusters)
- Cheaper costs with all heavy work on Hadoop side (we could have more modest Redshift cluster as a result)

## Advantages of ELT
- Redshift uses standard SQL, optimized for all relational operations, like joins and advanced inner queries, which are harder to express in map-reduce framework
- More popular technical skills needs, meaning it's easier to find engineers familiar with more standard database technologies, such as Redshift
- Scaling and parallelism made effective and easier

## References
- https://www.stitchdata.com/etldatabase/etl-transform/
- http://slawomirtulski.com/hive_redshift_test
