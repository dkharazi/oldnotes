## General Principles of Cloud Computing
- Most cloud computing services typically revolve around one (or more) of the following:
	- Compute power
	- Storage
	- Networking
	- Analytics
- Storage refers to a 

## Compute Power
- Compute power refers to a resource's ability to process some set of instructions (i.e. a program)
- CPUs and GPUs give us compute power
- Cloud services typically offer compute power in three different ways:
	1. Virtual Machine
	2. Container
	3. Serverless
- Virtual machines are more heavyweight, but are more isolated (since they try to emulate hardware)
- Containers are more lightweight, but are a little less isolated (since they try to emulate the operating system)
- Serverless computing refers to functions offered by Azure (or any cloud platform)
- VMs and containers are charged while they're running in most cloud models, even if the applications on them are idle
- Serverless functions are only charged when they're executed
- Serverless functions are ideal for automated tasks (such as email confirmations), but can't handle any piece of logic (whereas our code on containers or VMs can handle any piece of logic)

## Benefits of Cloud Services
- Flexible pricing model
	- They typically follow a pay-as-you-go or consumption-based pricing model
	- No upfront infrastructure costs
	- No need to manage costly infrastructure
	- Ability to seamlessly scale up or out (more servers or better parts) when needed
	- Ability to stop paying for resources that are no longer needed
- Scalable
	- Ability to scale vertically based on demand or workload
	- Ability to scale horizontally based on demand or workload
- Saves development time
	- When using the cloud, we're able to focus on building and deploying applications
- Reliable
	- We want to ensure fault tolerance
	- Data backups available
	- Distaster recovery
- Secure
	- Ensures physical security
	- Ensures digital security

## Expenditure
- Roughly, there are three types of expenses:
	- Operational expenditures
	- Capital expenditures
- Capital expenditure (or CapEx) refers to spending related to acquiring and maintaining fixed assets
- Operating expenditure (or OpEx) refers to spending related ot activities not directly associated with the production of goods or services
- The following are examples of capital expenditures:
	- Computer equipment
	- Buildings
	- Office equipment
	- Furniture
	- On-premises datacenter (servers, storage, etc.)
	- Owning software
- The following are examples of operational expenditures:
	- Payroll
	- Sales commissions
	- Employee benefits
	- Rent
	- Utilities
	- Leasing software 

## References
- https://docs.microsoft.com/en-us/azure/azure-functions/
- https://docs.microsoft.com/en-us/learn/modules/principles-cloud-computing/2-what-is-cloud-computing
