These are used to create EC2 instance placement strategies

Following ways are available:
1. Cluster
	1. all instances share the same hardware and are in the same AZ
	2. used when we need low latency and high network throughput
	3. use case: to complete big data tasks
2. Spread:
	1. all instances are in different hardware and can be present in diff AZ
	2. limit is 7 instances per AZ
	3. More fault tolerant than cluster because if one instance fails, the rest are still there
	4. provides high availability 
3. Partition
	1. mix of cluster and spread. instances are divided into rack (hardware). each rack contains multiple instances and racks can exist in different AZ.
	2. limit: 7 instances per rack per AZ
	3. use case: hdfs, hadoop and so on
 