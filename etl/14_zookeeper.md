## General Description
- ZooKeeper is a coordination service for distributed systems (i.e. HBase)
- Zookeeper can be found throughout the Hadoop ecosystem, and in other Apache software, such as Kafka
- Essentially, Zookeeper is a distributed tree (or can be thought of as a file system) intended to hold small pieces of data on each node (not to confused with server nodes, but rather represent tree nodes instead) called zNodes

## zNode
- A zNode are the tree nodes below the root directory known as "/"
- A zNode may act as both a file containing binary data and a directory with more zNodes as sub nodes
- Similar to other file systems, each zNode has some meta data, which includes any read and write premissions
- Each zNode is associated with an open session in its distributed system
- We can either have ephemeral or sequential zNodes
- An ephemeral zNode is a node that will disappear when the session of its owner ends
- A typical use-case for ephemeral nodes is when using Zookeeper for discovery of hosts in your distributed system
	- This implies sending "heartbeats" throughout the distributed system to see if new hosts are on the system or if any sessions have expired (and need to be removed)

## References
- https://www.elastic.co/blog/found-zookeeper-king-of-coordination 
