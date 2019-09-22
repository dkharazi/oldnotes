## General Description
- HBase is a distributed NoSQL database that is built on top of HDFS
- In other words, HBase provides real-time access to read and write data in HDFS
- We can think of HBase as the database form of our unstructured HDFS (file system)

## Components of HBase
1. HBase HMaster
	- Node that is responsible for negotiating load balancing across all regional servers and maintaining the state of its Hadoop clusters associated to it
	- It is not part of the actual data storage or retrieval path, but instead manages and monitors the states of the hadoop clusters
2. RegionServer
	- Nodes that are deployed to host data and process I/O requests
3. ZooKeeper
	- Nodes that coordinate, communicate, and share states between the HMaster nodes and RegionServer nodes
	- They are responsible for monitoring the statuses of any of these nodes by checking for "heartbeats" from the services
	- They coordinate any data retrieval between RegionServer nodes and are responsible for monitoring any session timeouts

## References
- https://www.quora.com/What-is-the-difference-between-HBASE-and-HDFS-2
