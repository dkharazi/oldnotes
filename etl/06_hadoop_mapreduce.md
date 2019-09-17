## General Description
- Hadoop MapReduce is a software framework for easily writing applications which process vast amounts of data in parallel on large clusters of commodity hardware in a reliable, fault-tolerant manner
- MapReduce is a distributed computing framework, whereas HDFS is a distributed storage framework
- This MapReduce processing is made up of two phases:
	1. A map function
		- For example, we will demonstrate the idea behind the map function using a word-counter example
		- The map function will take in single words from each split-up HDFS block one at a time as an input
		- The map function will output a key-value pair each time it is called, where the key is a tracked word, such as "the", and the value is the number of occurrences, such as 1
		- Since MapReduce is a distributed computing framework, map functions will be running on many computer notes across its cluster
	2. A reduce function
		- The reduce function take in a key and a list of values as its input
		- The reduce function takes care of grouping all of the same keys together (this is the shuffle task)
		- So, the word "the" will have multiple values in its list, which in this case would be {1, 1, 1, ..., 1}
		- The reduce function will output a key-value pair, such as {"the": 5} in our case

## Job Trackers and Task Trackers
- A JobTracker acts like a master-server and is responsible for complete execution of submitted jobs
- A TaskTracker performs the application (which includes map, shuffle, and reduce tasks)
- There are typically one JobTracker per application, and multiple TaskTrackers per application
- JobTrackers reside on the NameNode, whereas TaskTrackers reside on the DataNodes

## General Process
1. Client submits applications to the Job tracker
2. The JobTracker requests metadata from its NameNode to determine the location of the data
3. An application is divided into multiple tasks which are run by TaskTrackers on multiple DataNodes
3. The JobTracker locates TaskTracker nodes with available slots at or near the data
4. The JobTracker submits the split application tasks to the chosen TaskTracker nodes
5. The TaskTracker is respomsible for executing any individual task, which reside on every DataNode executing part of the job at this point
6. The TaskTracker will also send the progress report of the application to the JobTracker by sending heartbeat signals to the JobTracker
7. If there is not enough heartbeat signals in a given time, the JobTracker will assume the application has failed and reschedule the application to another TaskTracker
8. When the application is completed, the JobTracker updates its status to completed
9. Client applications can also poll the JobTracker for information now

## References
- https://hadoop.apache.org/docs/r1.2.1/mapred_tutorial.html
- https://www.guru99.com/introduction-to-mapreduce.html
- https://www.slideshare.net/cloudera/introduction-to-yarn-and-mapreduce-2
- https://www.reddit.com/r/explainlikeimfive/comments/r3mdn/eli5_mapreduce_and_hadoop/
