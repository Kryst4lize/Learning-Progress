## Timeline
![[RelationalDatabaseTimeline.png]]

| Commercial Databases                                                      | Open-source databases                                                                  | Cloud databases                                                        |
| ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Large corporations dominated relational database development              | Popularity has experienced a surge                                                     | Now dominate due to the rapid grow of internet developement            |
| Commercial RDBMS provide scalability, reliability, comprehensive solution | Is freely available to public                                                          | Adopt SaaS model for enhanced scalability                              |
| Commercial license enhance the popularity of relational database          | Allow to view, modify, distribute source code -> foster collaboration and transparency | Processes extensive volume, Provide built-in backup, recovery solution |
| Ex: IBM DB2, Oracle                                                       | Ex: MySQL, PostgreSQL, SQLite                                                          | Ex: Amazon RDS, Microsoft SQL Azure, and Oracle Cloud                  |
Definition:
- Is a set of related objects used to store, manage, and access data 
## Characteristic 
- Includes structured data stores in related tables
- Have links to minimize the data duplication
- Along with supporting system known as RDBMS (Relational Database Management System)
	Ex: IBM DB2, Microsoft SQL Server, Oracle, MySQL, PostgreSQL
--- 
## Scope of relational databases 
- OLAP (OnLine Analytic Processing)
	Including various storage solutions
	Focus on querying and analyzing large datasets
	Ex: Sourcing data from Customer Relationship Management (CRM) for generating sales)
- OLTP (OnLine Transaction Processing)
	Store high volume of operational data
	Ensures transactional integrity 
--- 
How to create a Relational database :
Using [[Entity Relationship Diagram (ERD)]] and convert it into tables
## Best Practices 
- Primary key designation:
	- Unique identify each record in the database
- Data validation: 
	- Ensure accuracy and consistency of data
	- Involves check for data types, ranges and formats
	- To ensure the collected data can be used [[Data Collection]]
- Default values
	- Streamline data entry 
	- Enhance records to analyze
- Use of views
	- Present a customized and simplified perspective of data
- Concurrency control
	- Manage access and modification to the data base
	- Prevent data conflict and inconsistency (between user read/write process)
---
Some Relational databases : [[Db2]] , [[MySQL]], [[PostgreSQL]]
Language : [[Struct Query Language (SQL)]]