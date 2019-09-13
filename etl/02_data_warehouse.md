## General Description
- A data warehouse is the storage dedicated to already modeled and structured data
- Examples of data you'd store in a data warehouse:
        - Sales data (which could be used by finance or marketing teams)
        - Expense data (which could be used by finance or reporting teams)
	- Transactional data (which could be used by reporting or pricing teams)

## Properties of Data Lakes
- General purpose: Typically stores data from data lake after its raw data has been transformed
- Most important use-case: Stores transformed data intended for operational and performance analytics
- Time to market: Hours and days
- Cost: Somewhat expensive
- Users: Very many users (typically data scientists, business users, etc.)
- Data growth: Below average volume and variety of data

## Differences between Data Lakes and Data Warehouses
1. They assist different data types
	- A data warehouse usually consists of data that has been extracted from transactional systems and is made up of quantitative metrics
	- A data lake usually consists of non-traditional data types, such as web server logs, social network activity, text, and images
2. They support different users
	- A data warehouse typically serves the BI needs of reporting teams, operational users, etc.
	- A data warehouse also serves the data science needs as a go-to source for data integration, data preparation, and data analytics
	- A data lake also serves the data science needs of analyzing much larger, multi-purpose data
	- A data lake usually serves the data engineering needs for storing data that will later be transformed and loaded into data warehouses
3. They have different hardware capabilities
	- A data warehouse maintains more specific data (taken from the data lake) and thus has a lesser need for expensive hardware
	- A data lake maintains all data and thus has a greater need for expensive hardware
4. They have different abilities to adapt to change
	- A data warehouse can adapt to change well, since the data transformation and loading process is so complex, but requires plenty of time and resources to prepare for and execute such development
	- A data lake is accessible to anyone due to its raw format and lack of structure

## References
- https://www.holistics.io/blog/data-lake-vs-data-warehouse-vs-data-mart/
