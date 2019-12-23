## Motivation
- Apache MapReduce, Apache HBase, and Apache Spark are all examples of distributed services
- These distributed services involve distributed processes
- ZooKeeper is a distributed service manager and coordinates these distributed processes

## General Description
- ZooKeeper is a type of distributed storage that acts as a coordination service for a distributed process
- Distributed services use ZooKeeper to:
	1. Ensure a cluster is synchronized
	2. Recover from partial failures (of distributed processes) within a cluster
- ZooKeeper stores and tracks information about a cluster to help ensure the cluster is synchronized
- ZooKeeper stores and tracks information about a cluster on different nodes (i.e. zNodes) to help recover from partial failures within a cluster
- The following are some examples of cluster information tracked by ZooKeeper:
	- Which node is the master?
	- What tasks are assigned to which workers?
	- Which workers are currenty available?
- Technically speaking, ZooKeeper is a distributed tree (or a file system) intended to hold small pieces of data on each node called zNodes
	- ZooKeeper nodes ≠ server nodes
	- Instead, ZooKeeper nodes represent tree nodes

## zNodes
- A zNode is a tree node below the root directory known as "/"
- A zNode may act as either a file containing binary data or a directory with more zNodes as sub-nodes
- Similar to other file systems, each zNode has some meta-data, which includes any read and write premissions
- Each zNode is associated with an open session in its distributed system
- We can either have ephemeral or persistent zNodes
- An ephemeral zNode is a ZooKeeper node that will disappear when the session of its owner ends
- A typical use-case for ephemeral zNodes is when using ZooKeeper for discovery of hosts in your distributed system
	- This implies sending "heartbeats" throughout the distributed system to see if new hosts are on the system or if any sessions have expired (and need to be removed)
- A persistent zNode is a ZooKeeper node that remains stored until explicitly deleted
- A typical use-case for persistent zNodes is when using ZooKeeper for assigning tasks to workers
	- Having a zNode for metadata (i.e. lists or queue of tasks for nodes)  must persist even if the master node crashes

## Example of ZooKeeper File System and zNodes

/
|
|____/master-1
|
|____/workers
	|
	|____/worker-1
	|
	|____/worker-2

- The above tree represents our ZooKeeper file system of zNodes
- master-1, worker-1, and worker-2 are considered zNodes
- The master-1 zNode will contain data about the master node, such as "master-1.foobar.com:2223", so we can identify the node and locate it within the cluster
- The worker-1 zNode will contain data about a worker node, such as "worker-3.foobar.com:2225", so we can identify the node and locate it within the cluster
- The worker-2 zNode will contain data about a worker node, such as "worker-567.foobar.com:2225", so we can identify the node and locate it within the cluster

## Specific ZooKeeper Use-Cases
- Nodes within clusters can crash because of hard-disk failures, network issues, etc.
- We need to know if a master node crashes within a cluster
	- We can use ZooKeeper to monitor a master node within a cluster to detect any crashes
	- ZooKeeper monitors a master node within a cluster by occasionally pinging the master node within its cluster (and saving the pinged data from a master node into a zNode)
- We need to fail over to a backup master node if the active master node crashes within a cluster
	- Assuming there are free master nodes available outside of the cluster (for backup purposes), we can use ZooKeeper to promote one of those nodes to the cluster's master node if the master node crashes
	- ZooKeeper coordinates with a master node within a cluster and a master node outside of a cluster by saving information about each master node into a zNode
- We need to know if a worker node crashes within a cluster
	- We can use ZooKeeper to monitor worker nodes within a cluster to detect any crashes
	- ZooKeeper monitors worker nodes within a cluster by occasionally pinging each worker node within its cluster (and saving the pinged data from a worker node into a zNode)
- We need to fail over to a backup worker node if the active worker node crashes within a cluster
	- Assuming there are other worker nodes within the cluster for backup purposes, we can use ZooKeeper to promote a backup worker node to the current worker node if the active worker node crashes
	- ZooKeeper coordinates between worker nodes within a cluster by saving information about each worker node within a cluster into a zNode
- We need to notify a distributed service of any failures
	- We can use ZooKeeper to monitor and coordinate nodes within a cluster to make sure nodes are replaced by backups if they crash
	- We can also use ZooKeeper to notify the distributed service to replace those backup nodes so we can replace more nodes in case there are failures in the future

## General ZooKeeper Use-Cases
- Master election
	- One node registers itself as an active master node, and holds a "lock" on that data
	- Other nodes cannot become an active master node until that lock is released
	- Only one node allowed to hold the lock at a time
	- ZooKeeper is responsible for making sure the above conditions are satisfied
- Group management
	- Tracking data about a node's availability
	- ZooKeeper is responsible for making sure the above condition is satisfied
- Crash detection
	- When tracking data about a node's availability, we need to ensure this data is ephemeral, meaning it will automatically go away if the node disconnects or crashes (this ensure data from old nodes doesn't pile up)
	- ZooKeeper is responsible for making sure the above condition is satisfied
- Metadata
	- A list of outstanding tasks is maintained (so when old nodes go down, the new nodes knows where to pick up from)
	- ZooKeeper is responsible for making sure the above condition is satisfied

## Use-Cases in Apache Software
- HBase
	- HBase uses ZooKeeper to monitor master nodes and worker nodes within a cluster, coordinating between master nodes and worker nodes if any failures occur, and notifying HBase if any failures occur so HBase can create new master and worker nodes
- MapReduce
	- MapReduce uses ZooKeeper to aid in high availability of ResourceManagers
- Flume
	- Flume uses ZooKeeper for configuration purposes
- Kafka
	- Kafka uses ZooKeeper for configuration management, synchronization, leader election, and tracking the status of its cluster nodes
- Spark
	- Spark uses ZooKeeper for configuration management and leader election

## ZooKeeper Architecture
- Each master node and worker node (in some distributed service, such as HBase, Kafka, etc.) will have its own ZooKeeper client (or zNode) monitoring it
- These zNodes would be hosted on its own ZooKeeper server
- Typically, we would have multiple ZooKeeper servers and replicate the zNodes across each ZooKeeper server
	- The zNodes will not write unless each zNode has been confirmed to have replicated consistent data to the majority of the servers
- We have multiple ZooKeeper servers in case a ZooKeeper server crashes (i.e. who's watching the watchers)
- A collection of ZooKeeper servers is called a ZooKeeper ensemble

## ZooKeeper Quorums
- A ZooKeeper quorum refers to the number of zNodes (or servers) that need to return consistent data in order for the data to be written to each zNode across the ZooKeeper ensemble
- If our ZooKeeper ensemble contains 5 servers, and we set the ZooKeeper quorum to equal 2, then we are leaving too much room for error, since the majority of servers may not have consistent data
- If our ZooKeeper ensemble contains 5 servers, and we set the ZooKeeper quorum to equal 3, then we are leaving enough room for error, since the majority of servers will always have consistent data
- If our ZooKeeper ensemble contains 5 servers, and we set the ZooKeeper quorum to equal 4, then we aren't leaving enough room for error, since nearly 100% of the servers will need to have consistent data
- Essentially, we need to configure the ZooKeeper quorum properly, in order to ensure data consistency
- And, we need to have to configure the number of servers in our ensemble properly, in order to ensure data redundancy

## References
- https://www.youtube.com/watch?v=gZj16chk0Ss
- https://www.elastic.co/blog/found-zookeeper-king-of-coordination
- https://stackoverflow.com/questions/10732834/why-do-we-need-zookeeper-in-the-hadoop-stack
- https://stackoverflow.com/questions/3662995/explaining-apache-zookeeper
- https://www.youtube.com/watch?v=gifeThkqHjg
- https://zookeeper.apache.org/doc/r3.1.2/zookeeperProgrammers.html
