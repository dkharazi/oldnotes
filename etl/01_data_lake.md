## General Description
- A data lake is the storage dedicated to dumping all forms of data generated in various parts of the business
- Examples of data you'd store in a data lake:
	- Structured data feeds
	- Chat logs
	- Emails
	- Images (as blobs)
	- Videos

## Properties of Data Lakes
- General purpose: Stores raw data that will be transformed and loaded into a data warehouse later
- Most important use-case: Stores raw data intended for predictive and advanced analytics
- Time to market: Weeks to Months
- Cost: Very expensive
- Users: Very few (some data scientists but mostly data engineers to transform and load the data into data warehouses)
- Data growth: Large volume and large variety

## Purpose of Data Lakes
- Data is typically stored inside of data lakes for two reasons:
	1. You need a cheap way to store a lot of different types of multi-purpose data
		- Example: Twitter in the the B2C space (Business to Customer)
			- They have texts, images, videos, links, etc. going out to customers
		- Example: Transactions, returns, refunds, etc.
	2. You don't have a plan for what to do with the data, but you believe there will be an intent to use it at some point in the future

## References
- https://www.holistics.io/blog/data-lake-vs-data-warehouse-vs-data-mart/
