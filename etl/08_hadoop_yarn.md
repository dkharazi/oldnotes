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
	- Containers
- Containers typically host any transformation (i.e. MapReduce job) of blocks, and receives the necessary blocks as input for any MapReduce job
- NodeManagers are responsible for overseeing its containers 

## Architecture for Resource Management
- The ResourceManager and the NodeManagers help fulfill the functionality of managing resources distributed to individual nodes
- The ResourceManager is responsible for:
	1. Initializing an ApplicationMaster and allocating it resources when an application are created
	2. Recording information about all of the resources available and allocated to applications in the cluster
- Typically, there is a single ResourceManager in a cluster, and it lives in its own node
- The NodeManager is the per-machine framework agent that is responsible for:
	1. Monitoring containers to make sure they come back up if any containers fail
	2. Frequently reporting the resource usage (cpu, memory, disk, network) of containers back to the ResourceManager so it's constantly updated
	3. Initializing containers on its node for applications to run on
- Typically, there is a single NodeManager in each node to monitor the resources

## Architecture for Job Scheduling
- The ApplicationMaster helps fulfill the functionality of scheduling jobs involving processing (i.e. MapReduce jobs)
- An ApplicationMaster is responsible for:
	1. Requesting for more or fewer resources from the ResourceManager and allocating those resources to the containers running the application
	2. Monitoring its application to see if they are finished or not
- Typically, there is only one ApplicationMaster in a node, and they are spread out throughout nodes across the cluster
- Containers will report the transformation status (i.e. MapReduce status) to the ApplicationMaster

## Typical Process
1. Client submits an application
2. The ResourceManager creates a job id for the application
3. The ResourceManager allocates a container to start the ApplicationMaster for that application
4. The ApplicationMaster requests resources for itself and its other containers from the ResourceManager
5. The ResourceManager requests the metadata of any blocks relevant to the application from the NameNode
6. The ResourceManager receives the relevant metadata from the NameNode and sends any requested information back to the ApplicationMaster
7. The ApplicationMaster notifies the NodeManager to launch containers
	- These containers will be dedicated to running the application (i.e. MapReduce job)
	- Containers running Map tasks will be typically run on the same nodes as the relevant blocks
	- Containers running the Reduce tasks will start after the Map tasks, and will sometimes run on other nodes for processing
8. The NodeManager monitors the node's status, the ApplicationMaster monitors the application's status, and the ResourceManager monitors the cluster's status
9. Once the processing is complete, the ApplicationMaster un-registers itself from the ResourceManager

## References
- https://hadoop.apache.org/docs/current/hadoop-yarn/hadoop-yarn-site/YARN.html
- https://docs.portworx.com/install-with-other/docker/stateful-applications/hadoopandhdfs/#introduction
- https://www.datadoghq.com/blog/hadoop-architecture-overview/#hdfs-architecture
- https://www.slideshare.net/cloudera/introduction-to-yarn-and-mapreduce-2
- https://stackoverflow.com/questions/50791008/when-do-yarn-and-namenode-interact
- https://www.geeksforgeeks.org/hadoop-yarn-architecture/
