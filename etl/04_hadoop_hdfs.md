## Description of Distributed File Systems
- A file system is a system of files used for storage
- A distributed file system is any file system that satisfies the following:
	- Provides access of files from multiple hosts
	- Provides access of files via a computer network
- A distributed file system is either managed locally or remotely

## Difference between File Systems and Database
- File systems imply storage of unstructured, unrelated data
- Databases imply storage of structured, related data
- Databases (or DBMS) have more overhead compared to file systems
- File systems tend to be more lightweight, since they aren't structured and don't have as much overhead
- For example, databases have schemas and built in operations for indexing, retrieving, and searching for data; whereas file systems do not have any of this overhead
- The data files in databases are formatted in its own way to provide querying capabilities (and other features of the system)
- The data files in a file system are formatted in its original, raw format

## Examples of locally managed distributed file systems:
- HDFS (HDFS can be managed remotely as well with additional configurations)
- Ceph
- Lustre

## Examples of remotely managed distributed file systems:
- AWS S3
- Google Cloud Storage
- Microsoft Azure

## HDFS
- HDFS is apart of the Hadoop ecosystem
- HDFS can be used as a standalone dfs from the Hadoop ecosystem
	- Example: We can use Spark as a computing engine and HDFS as our storage
- HDFS is a distributed file system designed to run on commodity hardware
- HDFS is highly fault-tolerant and is designed to be deployed on cheaper hardware
- HDFS provides high throughput access to application data and is suitable for applications with large data sets
- HDFS assumes that once a file is created/written, it will not be changed

## Goals of HDFS
- Handles hardware failure
- Provides streaming access to data sets
- Handles very large data sets
- Executes code on the machine on which the data is stores, instead of loading the data on the machine where the code lives
	- In other words, it makes more sense to move the smaller thing to the machine with the larger thing if they need to interact together
- Portable from one platform to another

## References
- https://en.wikipedia.org/wiki/Comparison_of_distributed_file_systems
- https://hadoop.apache.org/docs/r1.2.1/hdfs_design.html
- https://stackoverflow.com/questions/40601991/what-is-the-principle-of-code-moving-to-data-rather-than-data-to-code
- https://www.researchgate.net/figure/Apache-Hadoop-Ecosystem_fig3_307619823 
