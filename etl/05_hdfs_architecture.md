## General Architecture
- Hadoop's Distributed File System (HDFS) is represented as a collection of clusters
- HDFS clusters are made up of a collection of nodes
- An HDFS node represents an individual computer (or machine, unit of storage, etc.)
- HDFS nodes contain software components or files (i.e. data) from the file system
- These software components include a NameNode and DataNodes
- Huge files are split into small chunks known as data blocks
- Files that are larger than 128 MB are split apart into 128 MB blocks, and those blocks are stored across HDFS nodes, which are all managed by a namespace
- A namespace is made up of a filesystem tree and the metadata for all of the files amd directories within the tree
- Metadata contains things like the owners of the files, permission bits, block locations, block sizes, etc.

## NameNodes
- Every HDFS cluster has a single node dedicated to running NameNode
- A NameNode is a master server that:
	1. Regulates any client-requested access to files
	2. Manages the namespace of the file system
- More specifically, the main functions performed by a NameNode include:
	- Storing metadata of data files located within nodes across its cluster
		- For example, the NameNode is responsible for storing and monitoring file names, file paths, number of data blocks, block ids, block locations, number of replicas, DataNode related configurations, etc.
	- Managing the namespace of the file system
	- Regulating client access for data files when they send requests
	- Sending requested transformations to DataNodes for them to fulfill
	- Executing some operation performed on the namespace of the file system
		- For example, the NameNode is responsible for opening/closing files, renaming files, renaming directories, etc.
- The NameNode keeps metadata in memory for fast retrieval

## DataNodes
- Almost every HDFS node within its cluster has a single DataNode running on its node
- A DataNode is responsible for managing any file storage on the node it runs on
- A DataNode will handle and perform any instruction from the NameNode, such as reading, writing, deletion, and replication of the blocks on its node

---- DataNodes also contain NodeManagers, ApplicationMasters, and containers
---- DataNodes perform some transformation (i.e. MapReduce jobs) on containers

## Summary
- A client will send a request to a NameNode on a cluster
- The NameNode will then send that request to the appropriate DataNodes by analyzing the filesystem tree and metadata
- The DataNodes will then fulfill the request by performing the appropriate transformation
- In other words, the NameNode will manage the client's requests, and the DataNodes will then process those requests

## References
- https://hadoop.apache.org/docs/r1.2.1/hdfs_design.html
- https://www.slideshare.net/cloudera/introduction-to-yarn-and-mapreduce-2
- https://data-flair.training/blogs/data-block/
- https://stackoverflow.com/questions/23922878/what-is-the-meaning-of-namespace-and-metadata-which-were-used-in-hdfsnamenode
