## SMP Data Warehouse
- A symmetric multi-processing (or SMP) system is a tightly coupled multiprocessor system where processors share resources
- In other words, the processing of a system is done by a bunch of individual CPUs connected to one common operating system, shared memory, and I/O devices
- SMP is the primary parallel architecture employed in servers
- Traditional SMP data warehouses utilize ETL processesing

## MPP Data Warehouse
- A massively parallel processing (or MPP) system is a coordinated processing system where a single task is processed by multiple processors, and each of those processors use its own operating system and memory
- In other words, the data and processing power are split up among several different compute nodes (i.e. servers) anda managed by a single leader node
- Roughly, MPP can be thought of as a distributed database system, since the data is stored across tables (whereas hadoop stores data in HDFS, meaning the data is stored across files)
- The leader node manages all external and internal communication and is responsible for preparing query execution plans whenever a query is submitted to the cluster
- The compute nodes manage the data and fulfill any processing
- Once a query is submitted to the cluster, the typical MPP process looks like this:
	1. The leader node receives a query from a client
	2. The leader node prepares a query execution plan
	3. The leader node distributes query execution code to the relevant compute nodes
	4. The compute nodes will execute the actual query to receive intermediate results
	5. The compute nodes will return the intermediate results to the leader node
	6. The leader node will aggregate the results
	7. The leader node will return the aggregated results to the client
- MPP data warehouses utilize ELT processing
- Azure SQL Data Warehouse is an example of an MPP data warehouse

## Motivating ELT with MPP Data Warehouses
- We're fairly familiar with ETL jobs, which generally includes the following steps:
	1. Extract the data from some external source system
	2. Transform the data before we add any data into the data warehouse
	3. Export the transformed data into the data warehouse
- And an ELT job generally includes the following steps:
	1. Extract the data from some external source system
	2. Load the data into the data warehouse
	3. Transform the data within the data warehouse
- If we're extracting more data over time, it will take longer to load the data for ETL jobs due to the architecture of most ETL systems (i.e. SMP)
- If we transition over to an MPP data warehouse, then we're able to utilize ELT jobs due to the architecture of most ELT systems (i.e. MPP)
- Specifically, if we try to perform ELT jobs and transform data after it has been loaded into an SMP data warehouse, then it will be very slow to transform very large data (such as terabytes) since the data is all in one database
- On the other hand, if we try to perform an ELT job and transform data after it has been loaded into an MPP data warehouse, then it will be much faster to transform very large data, since the data is distributed across many databases and transformations become much faster
- These ELT jobs in an MPP data warehouse are still generally faster than any ETL job in an SMP data warehouse for very large data, since transforming data in a distributed manner (within an MPP data warehouse) is much faster than transforming data before we load it into the data warehouse (because the data would still all be in one place most likely)
- As stated previously, MPP are good for ELT jobs and SMP are good for ETL jobs
- Hadoop remains one of the best systems for processing large data, but can still be slow at processing joins (compared to RDBMS like MPP)

## Use-Cases for ETL and ELT
- ETL works really well for batch-load processing
- ELT works really well for streams of data (i.e. loading single instances of data rapidly)
- As stated previously, MPP are good for ELT jobs and SMP are good for ETL jobs
- Hadoop remains one of the best systems for processing large data, but can still be slow at processing joins (compared to RDBMS like MPP)

## Azure Data Warehouse Technologies
- Azure SQL Data Warehouse is a tool used for creating and managing data warehouses in Azure
- Azure SQL Database is a tool used for creating and managing databases in Azure
- Azure Data Studio is a SQL editor used for connecting and querying Azure SQL Data Warehouse and Azure SQL Database
- Azure Data Factory is a tool used for scheduling or orchestrating movement and transformation of data in an automated fashion (i.e. moving data between SQL Data Warehouse and SQL Database)
- Polybase is a tool used for moving data to and from Hadoop, Azure Blob Storage, Azure Data Lake, and other unstructured non-relational tables

## When to Use Azure SQL DW and Azure SQL DB
- Azure SQL Database is optimized for the following:
	- Performing CRUD operations for some running web application
	- Optimized for OLTP operations, meaning many small requests to the database
	- In other words, optimized for transactional usage
- Azure SQL Data Warehouse is optimized for the following:
	- Performing a few complex queries on a large amount of historical data
	- Optimized for OLAP operation, meaning few large requests to the database
	- In other words, optimized for analytical usage

## Set up a SQL Data Warehouse
1. Create a resource in the Azure portal
2. Select SQL Data Warehouse in the Marketplace
3. Under the Basics tab, include the following information:
	- Subscription
	- Resource group
	- Data warehouse name
	- Server
4. Under the Select Performance Level field, select Gen2DW100c
5. Review + Create

## Add a Client IP Address
1. After the SQL Data Warehouse instance is provisioned, open it by selecting Go To Resource
2. At the top of the Overview pane, select the Server Name link to go to the associated SQL Server instance
3. Select Firewalls and Virtual Networks
4. Add Client IP

## Create Connections in Azure Data Studio
1. Select your data warehouse from the resource group in the Azure portal
2. Copy the server name for the data warehouse
3. Add a new connection in Azure Data Studio
4. Enter the following information:
	- Connection type
	- Server (taken from the server name from step 2)
	- Authentication type (e.g. SQL Login)
	- User name
	- Password
	- Database
5. Connect

## Install Azure CLI for macOS
1. Install Azure CLI
```
brew update && brew install azure-cli
```
2. Log in to Azure CLI in Azure CLI
```
az login
```
3. Run an bash script in Azure CLI
```
./path_to_file/test.sh
```

## Add a User to Azure SQL Data Warehouse
1. Create the following queries for the database within either Azure SQL Data Warehouse or Azure Data Studio
2. Create a new server login (so the user can access the server)
```
CREATE LOGIN example_user_login WITH PASSWORD = 'Str0ng_password';
```
3. Create a new database login (so the user can access the database)
```
CREATE USER example_user_name FOR LOGIN example_user_login;
```
4. Allow user to read data from Azure SQL Data Warehouse
```
EXEC sp_addrolemember 'db_datareader', 'example_user_name';
```

## Create a Distributed Table in Azure Data Studio
- Create a hash distributed table
```
(
	[EmployeeID] int NOT NULL,
	[EmployeeName] varchar(30) NOT NULL,
	[DOB] date NOT NULL,
	[Address] varchar(50) NOT NULL,
	[BloodGroup] nvarchar(2) NOT NULL
)
WITH
(
	CLUSTERED COLUMNSTORE INDEX,
	DISTRIBUTION = HASH([EmployeeID])
);
```
- Or create a round-robin distributed table
```
(
	[EmployeeID] int NOT NULL,
	[EmployeeName] varchar(30) NOT NULL,
	[DOB] date NOT NULL,
	[Address] varchar(50) NOT NULL,
	[BloodGroup] nvarchar(2) NOT NULL
)
WITH
(
	CLUSTERED COLUMNSTORE INDEX,
	DISTRIBUTION = ROUND_ROBIN
);
```
- Or create a replicated (distributed) table
```
(
	[EmployeeID] int NOT NULL,
	[EmployeeName] varchar(30) NOT NULL,
	[DOB] date NOT NULL,
	[Address] varchar(50) NOT NULL,
	[BloodGroup] nvarchar(2) NOT NULL
)
WITH
(
	CLUSTERED COLUMNSTORE INDEX,
	DISTRIBUTION = REPLICATE
);
```

## Load Data using Data Factory
1. Locate the SQL Data Warehouse instance in the Azure portal
2. Select Load Data under the Common Tasks tab
3. Select Azure Data Factory
4. Create a Data Factory
5. Specify the following details:
	- Data Factory name
	- Subscription
	- Select resource group
	- Select region
	- Select load data
6. Specify the following configurations:
	- Task name
	- Task description
	- Task cadence
	- Expiration time
7. Select the data source
8. Select the destination

## References
- https://docs.microsoft.com/en-us/azure/sql-data-warehouse/design-elt-data-loading
- https://cloudblogs.microsoft.com/sqlserver/2014/07/30/transitioning-from-smp-to-mpp-the-why-and-the-how/
- https://www.flydata.com/blog/introduction-to-massively-parallel-processing/
- https://hevodata.com/blog/redshift-architecture/
- https://0x0fff.com/hadoop-vs-mpp/
- https://stackoverflow.com/questions/21900185/what-are-oltp-and-olap-what-is-the-difference-between-them
- https://docs.microsoft.com/en-us/sql/relational-databases/polybase/polybase-guide?view=sql-server-ver15
