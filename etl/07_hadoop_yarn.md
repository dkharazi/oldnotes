## General Description
- YARN is a platform responsible for managing computing resources in clusters and using them for scheduling users’ applications
	- An application is either a single job or a collection of jobs
	- A job can be thought of as some user-requested transformation (i.e. MapReduce job)
- YARN is subproject of the Hadoop ecosystem
- Essentialy, YARN fulfills two functionalities:
	1. Manages the resources distributed to nodes, and thus applications as well
		- Achieves this by constantly monitoring resources via NodeManagers
	2. Schedules jobs involving processing

## General Architecture
- YARN is made up of many different nodes and separate daemons living on those nodes across a cluster
	- A node represents a single computer/machine
	- A cluster represents a collection of nodes all interconnected with each other
- These daemons include the following:
	- ResourceManager
	- NodeManagers
	- ApplicationMasters
	- Containers (i.e. HDFS containers)
- Containers typically contain the HDFS data (DataNodes), or hosts any transformation of the data

## Architecture for Resource Management
- The ResourceManager and the NodeManagers help fulfill the functionality of managing resources distributed to individual nodes
- The ResourceManager records information about all of the resources available and allocated to applications in the cluster
- Typically, there is a single ResourceManager in a cluster, and it lives in its own node
- The NodeManager is the per-machine framework agent that is responsible for:
	1. Monitoring containers to make sure they come back up if any containers fail
	2. Frequently reporting the resource usage (cpu, memory, disk, network) of containers back to the ResourceManager so it's constantly updated
- Typically, there is a single NodeManager in each node to monitor the resources

## Architecture for Job Scheduling
- The ApplicationMaster helps fulfill the functionality of scheduling jobs involving processing (i.e. MapReduce jobs)
- The ApplicationMaster is responsible for:
	1. Requesting for more or fewer resources from the ResourceManager and allocating them to the containers running the applications
	2. Monitoring the applications to see if they are finished or not
- Typically, there is only one ApplicationMaster in a node, and they are spread out throughout nodes across the cluster
- Containers will report the transformation status (i.e. MapReduce status) to the ApplicationMaster
- Containers live on nodes

## References
- https://hadoop.apache.org/docs/current/hadoop-yarn/hadoop-yarn-site/YARN.html
- https://docs.portworx.com/install-with-other/docker/stateful-applications/hadoopandhdfs/#introduction
